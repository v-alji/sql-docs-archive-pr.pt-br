---
title: Tuplas | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 35b629ae-b1ef-44b1-b556-96956aeb56e7
author: minewiskan
ms.author: owend
ms.openlocfilehash: c39d03d60cb66f3b2e26b2e660bd85f4e5e9d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683752"
---
# <a name="tuples"></a><span data-ttu-id="38cc3-102">Tuplas</span><span class="sxs-lookup"><span data-stu-id="38cc3-102">Tuples</span></span>
  <span data-ttu-id="38cc3-103">Uma tupla identifica exclusivamente uma fatia de dados de um cubo.</span><span class="sxs-lookup"><span data-stu-id="38cc3-103">A tuple uniquely identifies a slice of data from a cube.</span></span> <span data-ttu-id="38cc3-104">A tupla é formada por uma combinação de membros de dimensão, contanto que não haja dois ou mais membros pertencentes à mesma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="38cc3-104">The tuple is formed by a combination of dimension members, as long as there are no two or more members that belong to the same hierarchy.</span></span>  
  
## <a name="implicit-or-default-attribute-members-in-a-tuple"></a><span data-ttu-id="38cc3-105">Membros de atributo implícitos ou padrão em uma tupla</span><span class="sxs-lookup"><span data-stu-id="38cc3-105">Implicit or default attribute members in a tuple</span></span>  
 <span data-ttu-id="38cc3-106">Ao definir uma tupla em uma consulta ou expressão MDX, você não precisa explicitamente incluir o membro de atributo de cada hierarquia de atributo.</span><span class="sxs-lookup"><span data-stu-id="38cc3-106">When defining a tuple in an MDX query or expression, you do not need to explicitly include the attribute member from every attribute hierarchy.</span></span> <span data-ttu-id="38cc3-107">Se um membro de uma hierarquia de atributo não for explicitamente incluído em uma consulta ou em uma expressão, o membro padrão para aquela hierarquia de atributo será o membro de atributo implicitamente incluso na tupla.</span><span class="sxs-lookup"><span data-stu-id="38cc3-107">If a member from an attribute hierarchy is not explicitly included in a query or an expression, the default member for that attribute hierarchy is the attribute member implicitly included in the tuple.</span></span> <span data-ttu-id="38cc3-108">Salvo indicação contrária explicitamente definida em um cubo, o membro padrão para cada hierarquia de atributo é o membro (All), se houver um membro (All).</span><span class="sxs-lookup"><span data-stu-id="38cc3-108">Unless otherwise explicitly defined in a cube, the default member for every attribute hierarchy is the (All) member, if an (All) member exists.</span></span> <span data-ttu-id="38cc3-109">Se não houver um membro (All) em uma hierarquia de atributo, o membro padrão será um membro do nível superior da hierarquia de atributo.</span><span class="sxs-lookup"><span data-stu-id="38cc3-109">If an (All) member does not exist within an attribute hierarchy, the default member is a member of the attribute hierarchy's top level.</span></span> <span data-ttu-id="38cc3-110">A medida padrão é a primeira medida especificada no cubo, salvo se uma medida padrão estiver explicitamente definida.</span><span class="sxs-lookup"><span data-stu-id="38cc3-110">The default measure is the first measure specified in the cube, unless a default measure is explicitly defined.</span></span> <span data-ttu-id="38cc3-111">Para obter mais informações, consulte [Definir um membro padrão](../attribute-properties-define-a-default-member.md) e [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span><span class="sxs-lookup"><span data-stu-id="38cc3-111">For more information, see [Define a Default Member](../attribute-properties-define-a-default-member.md) and [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span></span>  
  
 <span data-ttu-id="38cc3-112">Por exemplo, a tupla a seguir identifica uma célula única no banco de dados do Adventure Works, definindo explicitamente um membro único da dimensão Medidas.</span><span class="sxs-lookup"><span data-stu-id="38cc3-112">For example, the following tuple identifies a single cell in the Adventure Works database by explicitly defining only a single member of the Measures dimension.</span></span>  
  
```  
(Measures.[Reseller Sales Amount])  
```  
  
 <span data-ttu-id="38cc3-113">O exemplo anterior identifica exclusivamente a célula que consiste no membro Valor das Vendas do Revendedor da dimensão Medidas e o membro padrão de cada hierarquia de atributo no cubo.</span><span class="sxs-lookup"><span data-stu-id="38cc3-113">The previous example uniquely identifies the cell consisting of the Reseller Sales Amount member from the Measures dimension and the default member from every attribute hierarchy in the cube.</span></span> <span data-ttu-id="38cc3-114">O membro padrão é o membro (All) para cada hierarquia de atributo diferente da hierarquia de atributo Moeda de Destino.</span><span class="sxs-lookup"><span data-stu-id="38cc3-114">The default member is the (All) member for every attribute hierarchy other than the Destination Currency attribute hierarchy.</span></span> <span data-ttu-id="38cc3-115">O membro padrão da hierarquia Moeda de Destino é o membro Dólar (EUA) (esse membro padrão está definido no script MDX no cubo Adventure Works).</span><span class="sxs-lookup"><span data-stu-id="38cc3-115">The default member for the Destination Currency hierarchy is the US Dollar member (this default member is defined in the MDX script for the Adventure Works cube).</span></span>  
  
 <span data-ttu-id="38cc3-116">A consulta a seguir retorna o valor da célula referenciada pela tupla especificada no exemplo anterior ($80.450.596,98).</span><span class="sxs-lookup"><span data-stu-id="38cc3-116">The following query returns the value for the cell referenced by the tuple specified in the previous example, ($80,450.596.98).</span></span>  
  
```  
SELECT   
Measures.[Reseller Sales Amount] ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="38cc3-117">Quando você especifica um eixo para um conjunto (nesse caso, composto por uma tupla única) em uma consulta, você deve começar especificando um conjunto para o eixo da coluna antes de especificar um conjunto para o eixo de linhas.</span><span class="sxs-lookup"><span data-stu-id="38cc3-117">When you specify an axis for a set (in this case composed of a single tuple) in a query, you must begin by specifying a set for the column axis before specifying a set for the row axis.</span></span> <span data-ttu-id="38cc3-118">O eixo da coluna também pode ser referido como *eixo (0)* ou simplesmente *0*.</span><span class="sxs-lookup"><span data-stu-id="38cc3-118">The column axis can also be referred to as *axis(0)* or simply *0*.</span></span> <span data-ttu-id="38cc3-119">Para obter mais informações sobre consultas MDX, consulte [A consulta MDX básica &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="38cc3-119">For more information about MDX queries, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
### <a name="tuples-as-values-or-member-references"></a><span data-ttu-id="38cc3-120">Tuplas como valores ou referências de membro</span><span class="sxs-lookup"><span data-stu-id="38cc3-120">Tuples as values or member references</span></span>  
 <span data-ttu-id="38cc3-121">Você pode usar uma tupla em uma consulta para retornar o valor na célula que é referenciado pela tupla, como no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="38cc3-121">You can use a tuple in a query to return the value in the cell that is referenced by the tuple, as in the previous example.</span></span> <span data-ttu-id="38cc3-122">Ou você pode usar uma tupla em uma expressão para explicitamente se referir aos membros especificados na tupla.</span><span class="sxs-lookup"><span data-stu-id="38cc3-122">Or you can use a tuple in an expression to explicitly refer to the members specified in the tuple.</span></span> <span data-ttu-id="38cc3-123">A consulta ou a expressão podem utilizar funções que retornam ou consomem tuplas.</span><span class="sxs-lookup"><span data-stu-id="38cc3-123">The query or the expression can utilize functions that either return or consume tuples.</span></span> <span data-ttu-id="38cc3-124">Uma tupla pode ser usada para se referir ao valor da célula que a tupla especifica, ou especificar uma combinação de membros, quando utilizada em uma função.</span><span class="sxs-lookup"><span data-stu-id="38cc3-124">A tuple can be used to either refer to the value of the cell that the tuple specifies, or to specify a combination of members when utilized in a function.</span></span>  
  
### <a name="tuple-dimensionality"></a><span data-ttu-id="38cc3-125">Dimensionalidade de tupla</span><span class="sxs-lookup"><span data-stu-id="38cc3-125">Tuple dimensionality</span></span>  
 <span data-ttu-id="38cc3-126">A *dimensionalidade* de uma tupla se refere à sequência ou ordem dos membros na tupla.</span><span class="sxs-lookup"><span data-stu-id="38cc3-126">The *dimensionality* of a tuple refers to the sequence or order of the members in the tuple.</span></span> <span data-ttu-id="38cc3-127">Como os membros implícitos sempre ocorrem na mesma ordem, na maioria das vezes a dimensionalidade é considerada em termos dos membros explicitamente definidos da tupla.</span><span class="sxs-lookup"><span data-stu-id="38cc3-127">Since the implicit members always occur in the same order, dimensionality is most often thought of in terms of the explicitly defined members of the tuple.</span></span> <span data-ttu-id="38cc3-128">A ordenação dos membros da tupla é importante quando você define um conjunto de tuplas.</span><span class="sxs-lookup"><span data-stu-id="38cc3-128">The ordering of the members of the tuple is important when you define a set of tuples.</span></span> <span data-ttu-id="38cc3-129">O exemplo a seguir inclui dois membros em uma tupla no eixo da coluna.</span><span class="sxs-lookup"><span data-stu-id="38cc3-129">The following example includes two members in a tuple on the column axis.</span></span>  
  
```  
SELECT   
([Measures].[Reseller Sales Amount],[Date].[Calendar Year].[CY 2004]) ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="38cc3-130">Quando você especificar explicitamente um membro em uma tupla de mais de uma dimensão, você deve incluir toda a tupla entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="38cc3-130">When you explicitly specify a member in a tuple from more than one dimension, you must include the entire tuple in parentheses.</span></span> <span data-ttu-id="38cc3-131">Ao especificar somente um membro único em uma tupla, os parênteses são opcionais.</span><span class="sxs-lookup"><span data-stu-id="38cc3-131">When only specifying a single member in a tuple, parentheses are optional.</span></span>  
  
 <span data-ttu-id="38cc3-132">A tupla na consulta no exemplo anterior especifica o retorno da célula do cubo na interseção da Medida do Valor das Vendas do Revendedor da dimensão Medidas e o membro CY 2004 da hierarquia de atributo Ano Civil na dimensão Data.</span><span class="sxs-lookup"><span data-stu-id="38cc3-132">The tuple in the query in the previous example specifies the return of the cube cell at the intersection of the Reseller Sales Amount Measure of the Measures dimension and the CY 2004 member of the Calendar Year attribute hierarchy in the Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38cc3-133">Um membro de atributo pode ser referido por seu nome de membro ou sua chave de membro.</span><span class="sxs-lookup"><span data-stu-id="38cc3-133">An attribute member can be referred by either its member name or its member key.</span></span> <span data-ttu-id="38cc3-134">No exemplo anterior, você poderia substituir a referência [CY 2004] por &[2004].</span><span class="sxs-lookup"><span data-stu-id="38cc3-134">In the previous example, you could replace the reference to [CY 2004] with &[2004].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cc3-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38cc3-135">See Also</span></span>  
 <span data-ttu-id="38cc3-136">[Conceitos principais em MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="38cc3-136">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="38cc3-137">[Espaço do cubo](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="38cc3-137">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="38cc3-138">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="38cc3-138">[Autoexists](autoexists.md) </span></span>  
 [<span data-ttu-id="38cc3-139">Trabalhando com membros, tuplas e conjuntos &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="38cc3-139">Working with Members, Tuples, and Sets &#40;MDX&#41;</span></span>](working-with-members-tuples-and-sets-mdx.md)  
  
  
