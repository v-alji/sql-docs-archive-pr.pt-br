---
title: Gerenciando escopo e contexto (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], context
- scope [MDX]
- CALCULATE statement
- This function [MDX]
- SCOPE statement
- scripts [MDX], scope
ms.assetid: 631e7c20-8be9-4c35-8609-76516aef19d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7cf1e6cea8df00b632e114a5a8756373738ca6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572745"
---
# <a name="managing-scope-and-context-mdx"></a><span data-ttu-id="fc10c-102">Gerenciando escopo e contexto (MDX)</span><span class="sxs-lookup"><span data-stu-id="fc10c-102">Managing Scope and Context (MDX)</span></span>
  <span data-ttu-id="fc10c-103">No [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , um script MDX pode se aplicar a todo o cubo ou a partes específicas do cubo, em pontos específicos dentro da execução do script do.</span><span class="sxs-lookup"><span data-stu-id="fc10c-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script can apply to the entire cube, or to specific portions of the cube, at specific points within the execution of the script.</span></span> <span data-ttu-id="fc10c-104">O script MDX pode adotar uma abordagem em camadas dos cálculos em um cubo usando passagens de cálculo.</span><span class="sxs-lookup"><span data-stu-id="fc10c-104">The MDX script can take a layered approach to calculations within a cube through the use of calculation passes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc10c-105">Para obter mais informações sobre como as passagens de cálculo podem afetar os cálculos, consulte [Noções básicas sobre a ordem de passagem e a ordem de resolução &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="fc10c-105">For more information on how calculation passes can affect calculations, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="fc10c-106">Para controlar a passagem de cálculo, o escopo e o contexto de um script MDX, use especificamente a instrução CACULATE, a função `This` e a instrução SCOPE.</span><span class="sxs-lookup"><span data-stu-id="fc10c-106">To control the calculation pass, scope, and context within an MDX script, you specifically use the CACULATE statement, the `This` function, and the SCOPE statement.</span></span>  
  
## <a name="using-the-calculate-statement"></a><span data-ttu-id="fc10c-107">Usando a instrução CALCULATE</span><span class="sxs-lookup"><span data-stu-id="fc10c-107">Using the CALCULATE Statement</span></span>  
 <span data-ttu-id="fc10c-108">A instrução CALCULATE preenche cada célula do cubo com dados agregados.</span><span class="sxs-lookup"><span data-stu-id="fc10c-108">The CALCULATE statement populates each cell in the cube with aggregated data.</span></span> <span data-ttu-id="fc10c-109">Por exemplo, o script MDX padrão possui uma única instrução CALCULATE no início do script.</span><span class="sxs-lookup"><span data-stu-id="fc10c-109">For example, the default MDX script has a single CALCULATE statement at the beginning of the script.</span></span>  
  
 <span data-ttu-id="fc10c-110">Para obter mais informações sobre a sintaxe da instrução CALCULATE, consulte [Instrução CALCULATE &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span><span class="sxs-lookup"><span data-stu-id="fc10c-110">For more information on the syntax of the CALCULATE statement, see [CALCULATE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc10c-111">Se o script contiver uma instrução SCOPE com uma instrução CALCULATE, a linguagem MDX avaliará a instrução CALCULATE no contexto do subcubo definido pela instrução SCOPE e não com relação ao cubo inteiro.</span><span class="sxs-lookup"><span data-stu-id="fc10c-111">If the script contains a SCOPE statement that contains a CALCULATE statement, MDX evaluates the CALCULATE statement within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
## <a name="using-the-this-function"></a><span data-ttu-id="fc10c-112">Usando a função This</span><span class="sxs-lookup"><span data-stu-id="fc10c-112">Using the This Function</span></span>  
 <span data-ttu-id="fc10c-113">A função `This` permite a recuperação do subcubo atual dentro de um script MDX.</span><span class="sxs-lookup"><span data-stu-id="fc10c-113">The `This` function lets you retrieve the current subcube within an MDX script.</span></span> <span data-ttu-id="fc10c-114">Use a função `This` para configurar rapidamente o valor de células do subcubo atual para uma expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="fc10c-114">You can use the `This` function to quickly set the value of cells within the current subcube to an MDX expression.</span></span> <span data-ttu-id="fc10c-115">Com frequência, você usará a função `This` em conjunto com a instrução SCOPE para alterar o conteúdo de um subcubo específico durante uma passagem de cálculo específica.</span><span class="sxs-lookup"><span data-stu-id="fc10c-115">You often use the `This` function in conjunction with the SCOPE statement to change the contents of a specific subcube during a specific calculation pass.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc10c-116">Se o script contiver uma instrução SCOPE com uma função `This`, o MDX avaliará a função `This` no contexto do subcubo definido pela instrução SCOPE e não com relação ao cubo inteiro.</span><span class="sxs-lookup"><span data-stu-id="fc10c-116">If the script contains a SCOPE statement that contains a `This` function, MDX evaluates the `This` function within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
### <a name="this-function-example"></a><span data-ttu-id="fc10c-117">Exemplo da função This</span><span class="sxs-lookup"><span data-stu-id="fc10c-117">This Function Example</span></span>  
 <span data-ttu-id="fc10c-118">O exemplo de comando de script MDX a seguir utiliza a função `This` para aumentar o valor da medida Amount, no grupo de medidas Finanças do cubo de exemplo [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)], em 10% para os filhos do membro Redmond da dimensão Customer:</span><span class="sxs-lookup"><span data-stu-id="fc10c-118">The following MDX script command example uses the `This` function to increase the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension:</span></span>  
  
```  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="fc10c-119">Para obter mais informações sobre a sintaxe da `This` função, consulte [esta &#40;&#41;MDX ](/sql/mdx/this-mdx).</span><span class="sxs-lookup"><span data-stu-id="fc10c-119">For more information on the syntax of the `This` function, see [This &#40;MDX&#41;](/sql/mdx/this-mdx).</span></span>  
  
## <a name="using-the-scope-statement"></a><span data-ttu-id="fc10c-120">Usando a instrução SCOPE</span><span class="sxs-lookup"><span data-stu-id="fc10c-120">Using the SCOPE Statement</span></span>  
 <span data-ttu-id="fc10c-121">A instrução SCOPE define o subcubo atual que contém outras expressões MDX e instruções em um script MDX e especifica seu escopo.</span><span class="sxs-lookup"><span data-stu-id="fc10c-121">The SCOPE statement defines the current subcube that contains, and specifies the scope of, other MDX expressions and statements within an MDX script.</span></span> <span data-ttu-id="fc10c-122">A linguagem MDX avalia essas outras expressões e instruções MDX, incluindo a função `This` e a instrução CALCULATE, no contexto do subcubo.</span><span class="sxs-lookup"><span data-stu-id="fc10c-122">MDX evaluates this other MDX expressions and statements, including the `This` function and the CALCULATE statement, within the context of the subcube.</span></span>  
  
 <span data-ttu-id="fc10c-123">Uma instrução SCOPE é dinâmica, mas não é iterativa por natureza.</span><span class="sxs-lookup"><span data-stu-id="fc10c-123">A SCOPE statement is dynamic, but not iterative in nature.</span></span> <span data-ttu-id="fc10c-124">As instruções contidas em uma instrução SCOPO são executadas uma vez, mas o próprio subcubo pode ser determinado dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="fc10c-124">The statements contained within a SCOPE statement run once, but the subcube itself can be dynamically determined.</span></span> <span data-ttu-id="fc10c-125">Por exemplo, você tem um cubo chamado CuboExemplo.</span><span class="sxs-lookup"><span data-stu-id="fc10c-125">For example, you have a cube named SampleCube.</span></span> <span data-ttu-id="fc10c-126">Ao cubo CuboExemplo, aplica a instrução SCOPE a seguir para definir um subcubo que define o contexto como ALLMEMBERS na dimensão Medidas:</span><span class="sxs-lookup"><span data-stu-id="fc10c-126">Against the SampleCube cube, you apply the following SCOPE statement to define a subcube the defines the context as the ALLMEMBERS within the Measures dimension:</span></span>  
  
 `SCOPE([Measures].ALLMEMBERS);`  
  
 `THIS = [Measures].ALLMEMBERS.COUNT;`  
  
 `END SCOPE;`  
  
 <span data-ttu-id="fc10c-127">As instruções e expressões dessa instrução SCOPE são executadas uma vez.</span><span class="sxs-lookup"><span data-stu-id="fc10c-127">The statements and expressions within this SCOPE statement run once.</span></span>  
  
 <span data-ttu-id="fc10c-128">Agora, um usuário da empresa executa a consulta MDX a seguir que contém uma medida, chamada MedidaExistente, no cubo de CuboExemplo:</span><span class="sxs-lookup"><span data-stu-id="fc10c-128">Now, a business user runs the following MDX query that contains one measure, named ExistingMeasure, against the SampleCube cube:</span></span>  
  
 `WITH MEMBER [Measures].[NewMeasure] AS '1'`  
  
 `SELECT`  
  
 `[Measures].ALLMEMBERS ON COLUMNS,`  
  
 `[Customer].DEFAULTMEMBER ON ROWS`  
  
 `FROM`  
  
 `[SampleCube]`  
  
 <span data-ttu-id="fc10c-129">O conjunto de células retornado pela consulta é semelhante à saída mostrada na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fc10c-129">The cellset returned from the query resembles the output shown in the following table.</span></span>  
  
||<span data-ttu-id="fc10c-130">[MedidaExistente]</span><span class="sxs-lookup"><span data-stu-id="fc10c-130">[ExistingMeasure]</span></span>|<span data-ttu-id="fc10c-131">[NovaMedida]</span><span class="sxs-lookup"><span data-stu-id="fc10c-131">[NewMeasure]</span></span>|  
|-|-------------------------|--------------------|  
|<span data-ttu-id="fc10c-132">[Cliente]. [Todos]</span><span class="sxs-lookup"><span data-stu-id="fc10c-132">[Customer].[All]</span></span>|<span data-ttu-id="fc10c-133">2</span><span class="sxs-lookup"><span data-stu-id="fc10c-133">2</span></span>|<span data-ttu-id="fc10c-134">2</span><span class="sxs-lookup"><span data-stu-id="fc10c-134">2</span></span>|  
  
 <span data-ttu-id="fc10c-135">Analisando o conjunto de células retornado, observe como o valor MedidaExistente, incluído na instrução SCOPE do script MDX, foi atualizado dinamicamente depois que a medida NovaMedida foi definida.</span><span class="sxs-lookup"><span data-stu-id="fc10c-135">Looking at the returned cellset, notice how the ExistingMeasure value, included in the SCOPE statement within the MDX script, is dynamically updated after the measure NewMeasure was defined.</span></span>  
  
 <span data-ttu-id="fc10c-136">Uma instrução SCOPE pode ser aninhada em outra instrução SCOPE.</span><span class="sxs-lookup"><span data-stu-id="fc10c-136">A SCOPE statement can be nested within another SCOPE statement.</span></span> <span data-ttu-id="fc10c-137">No entanto, como a instrução SCOPE não é iterativa, a principal finalidade de aninhar instruções SCOPE é subdividir ainda mais um subcubo para um tratamento especial.</span><span class="sxs-lookup"><span data-stu-id="fc10c-137">However, as the SCOPE statement is not iterative, the primary purpose for nesting SCOPE statements is to further subdivide a subcube for special treatment.</span></span>  
  
### <a name="scope-statement-example"></a><span data-ttu-id="fc10c-138">Exemplo da instrução SCOPE</span><span class="sxs-lookup"><span data-stu-id="fc10c-138">SCOPE Statement Example</span></span>  
 <span data-ttu-id="fc10c-139">O exemplo de script MDX a seguir utiliza uma instrução SCOPE para definir o valor da medida Amount, do grupo de medidas Finance do cubo de exemplo [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] , 10% mais alto para os filhos do membro Redmond da dimensão Customer.</span><span class="sxs-lookup"><span data-stu-id="fc10c-139">The following MDX script example uses a SCOPE statement to sets the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension.</span></span> <span data-ttu-id="fc10c-140">No entanto, outra instrução SCOPE altera o subcubo para incluir a medida Quantia para os filhos do ano calendário 2002.</span><span class="sxs-lookup"><span data-stu-id="fc10c-140">However, another SCOPE statement changes the subcube to include the Amount measure for the children of the 2002 calendar year.</span></span> <span data-ttu-id="fc10c-141">Por fim, a medida Quantia é agregada somente a esse subcubo, deixando os valores agregados da medida Quantia dos outros anos calendários inalterados.</span><span class="sxs-lookup"><span data-stu-id="fc10c-141">Finally, the Amount measure is then aggregated only for that subcube, leaving the aggregated values for the Amount measure in other calendar years unchanged.</span></span>  
  
```  
/* Calculate the entire cube first. */  
CALCULATE;  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="fc10c-142">Para obter mais informações sobre a sintaxe da instrução SCOPE, consulte [Instrução SCOPE &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span><span class="sxs-lookup"><span data-stu-id="fc10c-142">For more information on the syntax of the SCOPE statement, see [SCOPE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc10c-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fc10c-143">See Also</span></span>  
 <span data-ttu-id="fc10c-144">[Referência de linguagem MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="fc10c-144">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 <span data-ttu-id="fc10c-145">[O script MDX básico &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="fc10c-145">[The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span></span>  
 [<span data-ttu-id="fc10c-146">Conceitos básicos de consulta MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fc10c-146">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
