---
title: Espaço do cubo | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c3a012b4-9ca0-4fb8-9c26-5ecc0e2e2b2b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6a6da73815f06aa5ab80f6ad5a9d06227ed842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572746"
---
# <a name="cube-space"></a><span data-ttu-id="0032e-102">Espaço de cubo</span><span class="sxs-lookup"><span data-stu-id="0032e-102">Cube Space</span></span>
  <span data-ttu-id="0032e-103">Espaço de cubo é o produto dos membros das hierarquias de atributo de um cubo com as medidas do cubo.</span><span class="sxs-lookup"><span data-stu-id="0032e-103">Cube space is the product of the members of a cube's attribute hierarchies with the cube's measures.</span></span> <span data-ttu-id="0032e-104">Portanto, o espaço de cubo é determinado pelo produto combinatório de todos os membros de hierarquia de atributo no cubo e as medidas do cubo e define o tamanho máximo do cubo.</span><span class="sxs-lookup"><span data-stu-id="0032e-104">Therefore, the cube space is determined by the combinatorial product of all attribute hierarchy members in the cube and the cube's measures and defines the maximum size of the cube.</span></span> <span data-ttu-id="0032e-105">É importante observar que esse espaço inclui todas as possíveis combinações de membros de hierarquia de atributo, inclusive combinações que poderiam ser consideradas impossíveis no mundo real, como combinações onde a cidade é Paris e os países são Inglaterra, Espanha, Japão, Índia ou qualquer outro.</span><span class="sxs-lookup"><span data-stu-id="0032e-105">It is important to note that this space includes all possible combinations of attribute hierarchy members; even combinations that might be deem as impossible in the real world i.e. combinations where the city is Paris and the countries are England or Spain or Japan or India or elsewhere.</span></span>  
  
## <a name="autoexists-and-cube-space"></a><span data-ttu-id="0032e-106">Autoexists e espaço de cubo</span><span class="sxs-lookup"><span data-stu-id="0032e-106">Autoexists and cube space</span></span>  
 <span data-ttu-id="0032e-107">O conceito de *autoexists* limita esse espaço de cubo às células que realmente existem.</span><span class="sxs-lookup"><span data-stu-id="0032e-107">The concept of *autoexists* limits this cube space to those cells that actually exist.</span></span> <span data-ttu-id="0032e-108">É possível que membros de uma hierarquia de atributo em uma dimensão não existam com membros de outra hierarquia de atributo na mesma dimensão.</span><span class="sxs-lookup"><span data-stu-id="0032e-108">Members of an attribute hierarchy in a dimension may not exist with members of another attribute hierarchy in the same dimension.</span></span>  
  
 <span data-ttu-id="0032e-109">Por exemplo, se você tiver um cubo com uma hierarquia de atributo Cidade, uma hierarquia de atributo País, e uma medida Valor de Vendas pela Internet, o espaço desse cubo somente vai incluir os membros que existem um com o outro.</span><span class="sxs-lookup"><span data-stu-id="0032e-109">For example, if you have a cube that has a City attribute hierarchy, a Country attribute hierarchy, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="0032e-110">Por exemplo, se a hierarquia de atributo Cidade incluir as cidades de Nova Iorque, Londres, Paris, Tóquio e Melbourne; e a hierarquia de atributo País incluir os países Estados Unidos, Reino Unido, França, Japão e Austrália; o espaço do cubo não incluirá o espaço (célula) na interseção Paris e Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="0032e-110">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="0032e-111">Ao consultar células que não existem, as células inexistentes retornarão nulas; ou seja, elas não poderão conter cálculos e você não poderá definir um cálculo que seja gravado nesse espaço.</span><span class="sxs-lookup"><span data-stu-id="0032e-111">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="0032e-112">Por exemplo, a instrução a seguir inclui células que não existem.</span><span class="sxs-lookup"><span data-stu-id="0032e-112">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0032e-113">Essa consulta usa a função [Membros (Conjunto) (MDX)](/sql/mdx/members-set-mdx) para retornar o conjunto de membros da hierarquia de atributo Sexo no eixo da coluna, e cruza esse conjunto com o conjunto especificado de membros da hierarquia de atributo Cliente no eixo de linhas.</span><span class="sxs-lookup"><span data-stu-id="0032e-113">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="0032e-114">Quando você executa a consulta anterior, a célula na interseção Aaron A. Allen e Feminino exibe um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="0032e-114">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="0032e-115">Similarmente, a célula na interseção Abigail Clark e Masculino exibe um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="0032e-115">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="0032e-116">Essas células não existem e não podem conter um valor, mas as células que não existem podem aparecer no resultado retornado por uma consulta.</span><span class="sxs-lookup"><span data-stu-id="0032e-116">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="0032e-117">Quando você usa a função [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) para retornar o produto vetorial de membros de hierarquia de atributo de hierarquias de atributo na mesma dimensão, o Autoexists limita as tuplas que são retornadas ao conjunto de tuplas que realmente existem, em vez de retornar um produto Cartesiano completo.</span><span class="sxs-lookup"><span data-stu-id="0032e-117">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="0032e-118">Por exemplo, execute e examine os resultados da execução da consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="0032e-118">For example, run and then examine the results from the execution of the following query.</span></span>  
  
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
>  <span data-ttu-id="0032e-119">Note que 0 é usado para designar o eixo da coluna, que é a forma abreviada de eixo (0) – que é o eixo da coluna.</span><span class="sxs-lookup"><span data-stu-id="0032e-119">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="0032e-120">A consulta anterior somente retorna células para membros de cada hierarquia de atributo na consulta que existe um com o outro.</span><span class="sxs-lookup"><span data-stu-id="0032e-120">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="0032e-121">A consulta anterior também pode ser escrita usando a nova \* variante da função [ \* (de interjunção) (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="0032e-121">The previous query can also be written using the new \* variant of the [\* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="0032e-122">A consulta anterior também poderia ser escrita da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0032e-122">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="0032e-123">Os valores das células retornadas serão idênticos, apesar de os metadados no conjunto de resultados serem diferentes.</span><span class="sxs-lookup"><span data-stu-id="0032e-123">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="0032e-124">Por exemplo, com a consulta anterior, a hierarquia País foi movida para o eixo do slicer (na cláusula WHERE) e, portanto, não aparece explicitamente no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0032e-124">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="0032e-125">Cada uma dessas três consultas anteriores demonstra o efeito do comportamento de existência automática no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0032e-125">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="user-defined-hierarchies-and-cube-space"></a><span data-ttu-id="0032e-126">Hierarquias definidas pelo usuário e espaço do cubo</span><span class="sxs-lookup"><span data-stu-id="0032e-126">User-Defined Hierarchies and Cube Space</span></span>  
 <span data-ttu-id="0032e-127">Os exemplos anteriores deste tópico definem posições no espaço do cubo, usando hierarquias de atributo.</span><span class="sxs-lookup"><span data-stu-id="0032e-127">The previous examples in this topic define positions in cube space by using attribute hierarchies.</span></span> <span data-ttu-id="0032e-128">Porém, você também pode definir uma posição no espaço do cubo usando hierarquias definidas pelo usuário que foram definidas com base em hierarquias de atributo em uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="0032e-128">However, you can also define a position in cube space by using user-defined hierarchies that have been defined based on attribute hierarchies in a dimension.</span></span> <span data-ttu-id="0032e-129">Uma hierarquia definida pelo usuário é uma hierarquia das hierarquias de atributo planejada para facilitar a procura de dados de cubo pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="0032e-129">A user-defined hierarchy is a hierarchy of attribute hierarchies designed to facilitate browsing of cube data by users.</span></span>  
  
 <span data-ttu-id="0032e-130">Por exemplo, a consulta `CROSSJOIN` na seção anterior também poderia ter sido escrita conforme apresentado a seguir:</span><span class="sxs-lookup"><span data-stu-id="0032e-130">For example, the `CROSSJOIN` query in the previous section could also have been written as follows:</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[Customer Geography].[State-Province].Members  
   )   
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="0032e-131">Na consulta anterior, a hierarquia Geografia do Cliente definida pelo usuário dentro da dimensão Cliente é usada para definir a posição no espaço do cubo que foi anteriormente definida usando uma hierarquia de atributo.</span><span class="sxs-lookup"><span data-stu-id="0032e-131">In the previous query, the Customer Geography user-defined hierarchy within the Customer dimension is used to define the position in cube space that was previously defined by using an attribute hierarchy.</span></span> <span data-ttu-id="0032e-132">A posição idêntica no espaço do cubo pode ser definida usando hierarquias de atributo ou hierarquias definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="0032e-132">The identical position in cube space can be defined by using either attribute hierarchies or user-defined hierarchies.</span></span>  
  
##  <a name="attribute-relationships-and-cube-space"></a><a name="AttribRelationships"></a><span data-ttu-id="0032e-133">Relações de atributo e espaço de cubo</span><span class="sxs-lookup"><span data-stu-id="0032e-133">Attribute Relationships and Cube Space</span></span>  
 <span data-ttu-id="0032e-134">Definindo relações de atributo entre atributos relacionados aprimora o desempenho da consulta (facilitando a criação de agregações apropriadas) e afeta o membro de uma hierarquia de atributo relacionada que aparece com um membro de hierarquia de atributo.</span><span class="sxs-lookup"><span data-stu-id="0032e-134">Defining attribute relationships between related attributes improves query performance (by facilitating the creation of appropriate aggregations) and affects the member of a related attribute hierarchy that appears with an attribute hierarchy member.</span></span> <span data-ttu-id="0032e-135">Por exemplo, quando você define uma tupla que inclui um membro da hierarquia de atributo Cidade e a tupla não define explicitamente o membro da hierarquia de atributo País, você poderia esperar que o membro padrão da hierarquia de atributo País seria o membro relacionado da hierarquia de atributo País.</span><span class="sxs-lookup"><span data-stu-id="0032e-135">For example, when you define a tuple that includes a member from the City attribute hierarchy and the tuple does not explicitly define the Country attribute hierarchy member, you might expect that the default Country attribute hierarchy member would be the related member of the Country attribute hierarchy.</span></span> <span data-ttu-id="0032e-136">Porém, isso só ocorrerá se uma relação de atributo estiver definida entre a hierarquia de atributo Cidade e a hierarquia de atributo País.</span><span class="sxs-lookup"><span data-stu-id="0032e-136">However, this is only true if an attribute relationship is defined between the City attribute hierarchy and the Country attribute hierarchy.</span></span>  
  
 <span data-ttu-id="0032e-137">O exemplo a seguir retorna o membro de uma hierarquia de atributo relacionada que não está explicitamente incluído na consulta.</span><span class="sxs-lookup"><span data-stu-id="0032e-137">The following example returns the member of a related attribute hierarchy that is not included explicitly in the query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Country.CurrentMember.Name  
SELECT Measures.x ON 0,  
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0032e-138">Observe que a `WITH` palavra-chave é usada com as funções [CurrentMember (MDX)](/sql/mdx/current-mdx) e [nome (MDX)](/sql/mdx/members-string-mdx) para criar um membro calculado para uso na consulta.</span><span class="sxs-lookup"><span data-stu-id="0032e-138">Notice that the `WITH` keyword is used with the [CurrentMember (MDX)](/sql/mdx/current-mdx) and [Name (MDX)](/sql/mdx/members-string-mdx) functions to create a calculated member for use in the query.</span></span> <span data-ttu-id="0032e-139">Para obter mais informações, consulte [A consulta MDX básica &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="0032e-139">For more information, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
 <span data-ttu-id="0032e-140">Na consulta anterior, o nome do membro da hierarquia de atributo País que está associado a cada membro da hierarquia de atributo Estado é retornado.</span><span class="sxs-lookup"><span data-stu-id="0032e-140">In the previous query, the name of the member of the Country attribute hierarchy that is associated with each member of the State attribute hierarchy is returned.</span></span> <span data-ttu-id="0032e-141">O membro País esperado é exibido (porque uma relação de atributo está definida entre os atributos Cidade e País).</span><span class="sxs-lookup"><span data-stu-id="0032e-141">The expected Country member appears (because an attribute relationship is defined between the City and Country attributes).</span></span> <span data-ttu-id="0032e-142">Porém, se nenhuma relação de atributo estivesse definida entre hierarquias de atributo na mesma dimensão, o membro (All) seria retornado, conforme ilustrado na consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="0032e-142">However, if no attribute relationship were defined between attribute hierarchies in the same dimension, the (All) member would be returned, as illustrated in the following query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Education.Currentmember.Name  
SELECT Measures.x  ON 0,   
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="0032e-143">Na consulta anterior, é retornado o membro (All) ("Todos os Clientes"), porque não existe nenhuma relação entre Educação e Cidade.</span><span class="sxs-lookup"><span data-stu-id="0032e-143">In the previous query, the (All) member ("All Customers") is returned, because there is no relationship between Education and City.</span></span> <span data-ttu-id="0032e-144">Portanto, o membro (All) da hierarquia de atributo Educação seria o membro padrão da hierarquia de atributo Educação usado em qualquer tupla envolvendo a hierarquia de atributo Cidade onde um membro Educação não é explicitamente fornecido.</span><span class="sxs-lookup"><span data-stu-id="0032e-144">Therefore, the (All) member of the Education attribute hierarchy would be the default member of the Education attribute hierarchy used in any tuple involving the City attribute hierarchy where an Education member is not explicitly provided.</span></span>  
  
## <a name="calculation-context"></a><span data-ttu-id="0032e-145">Contexto de cálculo</span><span class="sxs-lookup"><span data-stu-id="0032e-145">Calculation Context</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0032e-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0032e-146">See Also</span></span>  
 <span data-ttu-id="0032e-147">[Conceitos principais em MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="0032e-147">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="0032e-148">[Tuplas](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="0032e-148">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="0032e-149">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="0032e-149">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="0032e-150">[Trabalhando com membros, tuplas e conjuntos &#40;&#41;MDX](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="0032e-150">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="0032e-151">[Totais visuais e totais não visuais](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="0032e-151">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="0032e-152">[Referência de linguagem MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="0032e-152">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="0032e-153">Referência de expressões multidimensionais &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="0032e-153">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
