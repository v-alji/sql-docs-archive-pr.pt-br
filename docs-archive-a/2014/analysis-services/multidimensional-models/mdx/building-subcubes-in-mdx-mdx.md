---
title: Criando subcubos em MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], subcubes
- subcubes [MDX]
- filtered views [MDX]
- MDX [Analysis Services], subcubes
- Multidimensional Expressions [Analysis Services], subcubes
- CREATE SUBCUBE statement
ms.assetid: 5403a62b-99ac-4d83-b02a-89bf78bf0f46
author: minewiskan
ms.author: owend
ms.openlocfilehash: 653b4d30aa86f52179c7b13619ac4347aa65c339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575419"
---
# <a name="building-subcubes-in-mdx-mdx"></a><span data-ttu-id="423c0-102">Criando subcubos em MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="423c0-102">Building Subcubes in MDX (MDX)</span></span>
  <span data-ttu-id="423c0-103">Um subcubo é um subconjunto de um cubo representando uma exibição filtrada dos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="423c0-103">A subcube is a subset of a cube on representing a filtered view of the underlying data.</span></span> <span data-ttu-id="423c0-104">Limitando o cubo a um subcubo, é possível melhorar o desempenho das consultas.</span><span class="sxs-lookup"><span data-stu-id="423c0-104">By limiting the cube to a subcube, you can improve query performance.</span></span>  
  
 <span data-ttu-id="423c0-105">Para definir um subcubo, use a instrução [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) , como descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="423c0-105">To define a subcube, you use the [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) statement, as described in this topic.</span></span>  
  
## <a name="create-subcube-syntax"></a><span data-ttu-id="423c0-106">Sintaxe de CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="423c0-106">CREATE SUBCUBE Syntax</span></span>  
 <span data-ttu-id="423c0-107">Use a sintaxe a seguir para criar um subcubo:</span><span class="sxs-lookup"><span data-stu-id="423c0-107">Use the following syntax to create a subcube:</span></span>  
  
```  
CREATE SUBCUBE Subcube_Identifier AS Subcube_Expression  
```  
  
 <span data-ttu-id="423c0-108">A sintaxe de CREATE SUBCUBE é bem simples.</span><span class="sxs-lookup"><span data-stu-id="423c0-108">The CREATE SUBCUBE syntax is fairly simple.</span></span> <span data-ttu-id="423c0-109">O parâmetro *Subcube_Identifier* identifica o cubo que servirá de base para o subcubo.</span><span class="sxs-lookup"><span data-stu-id="423c0-109">The *Subcube_Identifier* parameter identifies the cube on which the subcube will be based.</span></span> <span data-ttu-id="423c0-110">O parâmetro *Subcube_Expression* seleciona a parte do cubo que se tornará o subcubo</span><span class="sxs-lookup"><span data-stu-id="423c0-110">The *Subcube_Expression* parameter selects the part of the cube that will become the subcube</span></span>  
  
 <span data-ttu-id="423c0-111">Criado um subcubo, ele passa a ser o contexto de todas as consultas MDX até que a sessão seja encerrada ou você execute a instrução [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) .</span><span class="sxs-lookup"><span data-stu-id="423c0-111">After you create a subcube, that subcube becomes the context for all MDX queries until either the session closes or you run the [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) statement.</span></span>  
  
### <a name="what-a-subcube-contains"></a><span data-ttu-id="423c0-112">O que um subcubo contém</span><span class="sxs-lookup"><span data-stu-id="423c0-112">What a Subcube Contains</span></span>  
 <span data-ttu-id="423c0-113">Embora a instrução CREATE SUBCUBE seja bem simples de usar, a instrução em si não mostra explicitamente todos os membros que se tornam parte integrante do subcubo.</span><span class="sxs-lookup"><span data-stu-id="423c0-113">Although the CREATE SUBCUBE statement is fairly simple to use, the statement itself does not explicitly show all the members that become part of a subcube.</span></span> <span data-ttu-id="423c0-114">Aplicam-se as regras a seguir na definição de um subcubo:</span><span class="sxs-lookup"><span data-stu-id="423c0-114">In defining a subcube, the following rules apply:</span></span>  
  
-   <span data-ttu-id="423c0-115">Se você incluir o membro `(All)` de uma hierarquia, incluirá todos os membros dessa hierarquia.</span><span class="sxs-lookup"><span data-stu-id="423c0-115">If you include the `(All)` member of a hierarchy, you include every member of that hierarchy.</span></span>  
  
-   <span data-ttu-id="423c0-116">Se você incluir qualquer membro, incluirá seus ascendentes e descendentes.</span><span class="sxs-lookup"><span data-stu-id="423c0-116">If you include any member, you include that member's ascendants and descendants.</span></span>  
  
-   <span data-ttu-id="423c0-117">Se você incluir todos os membros de um nível, incluirá todos os membros da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="423c0-117">If you include every member from a level, you include all members from the hierarchy.</span></span> <span data-ttu-id="423c0-118">Membros de outras hierarquias serão excluídos se eles não existirem com os membros do nível (por exemplo, uma hierarquia desequilibrada, como uma cidade, não contém clientes).</span><span class="sxs-lookup"><span data-stu-id="423c0-118">Members from other hierarchies will be excluded if those members do not exist with members from the level (for example, an unbalanced hierarchy such as a city that does not contain customers).</span></span>  
  
-   <span data-ttu-id="423c0-119">Um subcubo sempre conterá todos os membros `(All)` do cubo.</span><span class="sxs-lookup"><span data-stu-id="423c0-119">A subcube will always contain every `(All)` member from the cube.</span></span>  
  
 <span data-ttu-id="423c0-120">Além disso, valores de agregação de um subcubo são visualmente totalizados.</span><span class="sxs-lookup"><span data-stu-id="423c0-120">Additionally, aggregate values within the subcube are visually totaled.</span></span> <span data-ttu-id="423c0-121">Por exemplo, um subcubo contém `USA`, `WA`e `OR`.</span><span class="sxs-lookup"><span data-stu-id="423c0-121">For example, a subcube contains `USA`, `WA`, and `OR`.</span></span> <span data-ttu-id="423c0-122">O valor de agregação para `USA` será a soma de `{WA,OR}` , pois `WA` e `OR` são os únicos estados definidos pelo subcubo.</span><span class="sxs-lookup"><span data-stu-id="423c0-122">The aggregate value for `USA` will be the sum of `{WA,OR}` because `WA` and `OR` are the only states defined by the subcube.</span></span> <span data-ttu-id="423c0-123">Todos os outros estados serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="423c0-123">All other states will be ignored.</span></span>  
  
 <span data-ttu-id="423c0-124">Além disso, referências explicitas a células fora do subcubo retornarão valores de células que são avaliados no contexto do cubo inteiro.</span><span class="sxs-lookup"><span data-stu-id="423c0-124">Also, explicit references to cells outside the subcube return cell values that are evaluated in the context of the whole cube.</span></span> <span data-ttu-id="423c0-125">Por exemplo, você cria um subcubo limitado ao ano atual.</span><span class="sxs-lookup"><span data-stu-id="423c0-125">For example, you create a subcube that is limited to the current year.</span></span> <span data-ttu-id="423c0-126">Você usa a função [ParallelPeriod](/sql/mdx/parallelperiod-mdx) para comparar o ano atual ao anterior.</span><span class="sxs-lookup"><span data-stu-id="423c0-126">You then use the [ParallelPeriod](/sql/mdx/parallelperiod-mdx) function to compare the current year to the previous year.</span></span> <span data-ttu-id="423c0-127">A diferença nos valores será retornada mesmo que o valor do ano anterior esteja fora do subcubo.</span><span class="sxs-lookup"><span data-stu-id="423c0-127">The difference in values will be returned even though the previous year's value lies outside the subcube.</span></span>  
  
 <span data-ttu-id="423c0-128">Por fim, se o contexto original não for substituído, as funções de conjunto de uma subseleção serão avaliadas no contexto da subseleção.</span><span class="sxs-lookup"><span data-stu-id="423c0-128">Finally, if the original context is not overwritten, set functions evaluated in a subselect are evaluated in the context of the subselect.</span></span> <span data-ttu-id="423c0-129">Se o contexto for substituído, as funções de conjunto serão avaliadas no contexto do cubo inteiro.</span><span class="sxs-lookup"><span data-stu-id="423c0-129">If the context is overwritten, set functions are evaluated in the context of the whole cube.</span></span>  
  
## <a name="create-subcube-example"></a><span data-ttu-id="423c0-130">Exemplo de CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="423c0-130">CREATE SUBCUBE Example</span></span>  
 <span data-ttu-id="423c0-131">O exemplo a seguir cria um subcubo que restringe o cubo Orçamento às contas 4200 e 4300:</span><span class="sxs-lookup"><span data-stu-id="423c0-131">The following example creates a subcube that restricts the Budget cube to only accounts 4200 and 4300:</span></span>  
  
 `CREATE SUBCUBE Budget AS SELECT {[Account].[Account].&[4200], [Account].[Account].&[4300] } ON 0 FROM Budget`  
  
 <span data-ttu-id="423c0-132">Havendo um subcubo criado para a sessão, qualquer consulta subsequente será feita no subcubo, e não no cubo inteiro.</span><span class="sxs-lookup"><span data-stu-id="423c0-132">Having created a subcube for the session, any subsequent queries will be against the subcube, not the whole cube.</span></span> <span data-ttu-id="423c0-133">Por exemplo, você executa a consulta abaixo.</span><span class="sxs-lookup"><span data-stu-id="423c0-133">For example, you run the following query.</span></span> <span data-ttu-id="423c0-134">Ela retornará apenas os membros das contas 4200 e 4300.</span><span class="sxs-lookup"><span data-stu-id="423c0-134">This query will only return members from accounts 4200 and 4300.</span></span>  
  
 `SELECT [Account].[Account].Members ON 0, Measures.Members ON 1 FROM Budget`  
  
## <a name="see-also"></a><span data-ttu-id="423c0-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="423c0-135">See Also</span></span>  
 <span data-ttu-id="423c0-136">[Estabelecendo o contexto de cubo em uma consulta &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="423c0-136">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 [<span data-ttu-id="423c0-137">Conceitos básicos de consulta MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="423c0-137">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
