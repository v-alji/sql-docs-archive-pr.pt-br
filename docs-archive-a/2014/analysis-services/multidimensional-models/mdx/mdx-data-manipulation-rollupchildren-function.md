---
title: Trabalhando com a função RollupChildren (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], RollupChildren function
- RollupChildren function
- custom member properties [MDX]
- IIf function
ms.assetid: 03c624d4-f277-451d-9995-623a07ea2f86
author: minewiskan
ms.author: owend
ms.openlocfilehash: 341468d521cebe1fda33d73ea999f3b6571cb01e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683766"
---
# <a name="working-with-the-rollupchildren-function-mdx"></a><span data-ttu-id="f7ce3-102">Trabalhando com a função RollupChildren (MDX)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-102">Working with the RollupChildren Function (MDX)</span></span>
  <span data-ttu-id="f7ce3-103">A função MDX (Multidimensional Expressions) [RollupChildren](/sql/mdx/rollupchildren-mdx) [script for Search and Replace] acumula os filhos de um membro, aplicando um operador unário diferente a cada filho e retorna o valor desse ROLLUP como um número.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-103">The Multidimensional Expressions (MDX) [RollupChildren](/sql/mdx/rollupchildren-mdx) [Script for Search and Replace] function rolls up the children of a member, applying a different unary operator to each child, and returns the value of this rollup as a number.</span></span> <span data-ttu-id="f7ce3-104">O operador unário pode ser fornecido por uma propriedade do membro associada ao membro filho ou pode ser uma expressão de cadeia de caracteres fornecida diretamente para a função.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-104">The unary operator can be supplied by a member property associated with the child member, or the operator can be a string expression provided directly to the function.</span></span>  
  
## <a name="rollupchildren-function-examples"></a><span data-ttu-id="f7ce3-105">Exemplos da função RollupChildren</span><span class="sxs-lookup"><span data-stu-id="f7ce3-105">RollupChildren Function Examples</span></span>  
 <span data-ttu-id="f7ce3-106">O uso da função `RollupChildren` em instruções MDX é simples de explicar, mas seu efeito sobre consultas MDX pode ser bastante abrangente.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-106">The use of the `RollupChildren` function in Multidimensional Expressions (MDX) statements is simple to explain, but the effect of this function on MDX queries can be wide-ranging.</span></span>  
  
 <span data-ttu-id="f7ce3-107">O efeito da função `RollupChildren` ocorre em consultas MDX projetadas para executar a análise seletiva dos dados de um cubo.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-107">The effect of the `RollupChildren` function occurs in MDX queries designed to perform selective analysis on existing cube data.</span></span> <span data-ttu-id="f7ce3-108">Por exemplo, a tabela a seguir contém uma lista de membros filhos do membro pai Vendas líquidas, com seus operadores unários (representados pela propriedade de membro `UNARY_OPERATOR`) mostrados entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-108">For example, the following table contains a list of child members for the Net Sales parent member, with their unary operators (represented by the `UNARY_OPERATOR` member property) shown in parentheses.</span></span>  
  
|<span data-ttu-id="f7ce3-109">Membro pai</span><span class="sxs-lookup"><span data-stu-id="f7ce3-109">Parent member</span></span>|<span data-ttu-id="f7ce3-110">Membro filho</span><span class="sxs-lookup"><span data-stu-id="f7ce3-110">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="f7ce3-111">Vendas Líquidas</span><span class="sxs-lookup"><span data-stu-id="f7ce3-111">Net Sales</span></span>|<span data-ttu-id="f7ce3-112">Vendas internas (+)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-112">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="f7ce3-113">Lucros internos (-)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-113">Domestic Returns (-)</span></span><br /><br /> <span data-ttu-id="f7ce3-114">Exportações (+)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-114">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="f7ce3-115">Lucros de exportações (-)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-115">Foreign Returns (-)</span></span>|  
  
 <span data-ttu-id="f7ce3-116">O membro pai Vendas líquidas apresenta o total de vendas líquidas menos os valores brutos de vendas internas e exportações, sendo os lucros interno e de exportação subtraídos como parte do acúmulo.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-116">The Net Sales parent member currently provides a total of net sales minus the gross domestic and foreign sales values, with the domestic and foreign returns subtracted as part of the rollup.</span></span>  
  
 <span data-ttu-id="f7ce3-117">Porém, você quer gerar uma previsão rápida e fácil das vendas brutas internas e exportações mais 10%, ignorando os lucros interno e de exportações.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-117">However, you want to provide a quick and easy forecast of domestic and foreign gross sales plus 10%, ignoring the domestic and foreign returns.</span></span> <span data-ttu-id="f7ce3-118">Para calcular esse valor, pode usar a função `RollupChildren` de uma destas maneiras: com uma propriedade de membro personalizado ou com a função `IIf`.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-118">To calculate this value, you can use the `RollupChildren` function in one of two ways: with a custom member property or with the `IIf` function.</span></span>  
  
### <a name="using-a-custom-member-property"></a><span data-ttu-id="f7ce3-119">Usando uma propriedade de membro personalizado</span><span class="sxs-lookup"><span data-stu-id="f7ce3-119">Using a Custom Member Property</span></span>  
 <span data-ttu-id="f7ce3-120">Se o cálculo acumulado for uma operação realizada com frequência, um método seria criar uma propriedade membro capaz de armazenar o operador que será usado com cada filho para um função específica.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-120">If the rollup calculation is to be a frequently performed operation, one method is to create a member property that stores the operator that will be used for each child for a specific function.</span></span> <span data-ttu-id="f7ce3-121">A tabela a seguir exibe os operadores unários válidos e descreve o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-121">The following table displays valid unary operators and describes the expected result.</span></span>  
  
|<span data-ttu-id="f7ce3-122">Operador</span><span class="sxs-lookup"><span data-stu-id="f7ce3-122">Operator</span></span>|<span data-ttu-id="f7ce3-123">Resultado</span><span class="sxs-lookup"><span data-stu-id="f7ce3-123">Result</span></span>|  
|--------------|------------|  
|+|<span data-ttu-id="f7ce3-124">total = total + filho atual</span><span class="sxs-lookup"><span data-stu-id="f7ce3-124">total = total + current child</span></span>|  
|-|<span data-ttu-id="f7ce3-125">total = total – filho atual</span><span class="sxs-lookup"><span data-stu-id="f7ce3-125">total = total - current child</span></span>|  
|*|<span data-ttu-id="f7ce3-126">total = total \* filho atual</span><span class="sxs-lookup"><span data-stu-id="f7ce3-126">total = total \* current child</span></span>|  
|/|<span data-ttu-id="f7ce3-127">total = total / filho atual</span><span class="sxs-lookup"><span data-stu-id="f7ce3-127">total = total / current child</span></span>|  
|~|<span data-ttu-id="f7ce3-128">O filho não é usado no acúmulo.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-128">Child is not used in the rollup.</span></span> <span data-ttu-id="f7ce3-129">O valor do filho é ignorado.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-129">The child's value is ignored.</span></span>|  
  
 <span data-ttu-id="f7ce3-130">Por exemplo, uma propriedade de membro chamada `SALES_OPERATOR`) poderia ser criada e os seguintes operadores unários seriam atribuídos a ela, como mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-130">For example, a member property called `SALES_OPERATOR` could be created, and the following unary operators would be assigned to that member property, as shown in the following table.</span></span>  
  
|<span data-ttu-id="f7ce3-131">Membro pai</span><span class="sxs-lookup"><span data-stu-id="f7ce3-131">Parent member</span></span>|<span data-ttu-id="f7ce3-132">Membro filho</span><span class="sxs-lookup"><span data-stu-id="f7ce3-132">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="f7ce3-133">Vendas Líquidas</span><span class="sxs-lookup"><span data-stu-id="f7ce3-133">Net Sales</span></span>|<span data-ttu-id="f7ce3-134">Vendas internas (+)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-134">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="f7ce3-135">Lucros internos (~)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-135">Domestic Returns (~)</span></span><br /><br /> <span data-ttu-id="f7ce3-136">Exportações (+)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-136">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="f7ce3-137">Lucros de exportações (~)</span><span class="sxs-lookup"><span data-stu-id="f7ce3-137">Foreign Returns (~)</span></span>|  
  
 <span data-ttu-id="f7ce3-138">Com essa nova propriedade de membro, a seguinte instrução MDX executaria a operação de estimativa das vendas brutas com rapidez e eficiência (ignorando os lucros interno e de exportação):</span><span class="sxs-lookup"><span data-stu-id="f7ce3-138">With this new member property, the following MDX statement would perform the gross sales estimate operation quickly and efficiently (ignoring Foreign and Domestic returns):</span></span>  
  
```  
RollupChildren([Net Sales], [Net Sales].CurrentMember.Properties("SALES_OPERATOR")) * 1.1  
```  
  
 <span data-ttu-id="f7ce3-139">Quando a função é chamada, o valor de cada filho é aplicado ao total usando o operador armazenado na propriedade membro.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-139">When the function is called, the value of each child is applied to a total using the operator stored in the member property.</span></span> <span data-ttu-id="f7ce3-140">Os membros de lucros interno e de exportação são ignorados e o total acumulado retornado pela função `RollupChildren` é multiplicado por 1,1.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-140">The members for domestic and foreign returns are ignored, and the rollup total returned by the `RollupChildren` function is multiplied by 1.1.</span></span>  
  
### <a name="using-the-iif-function"></a><span data-ttu-id="f7ce3-141">Usando a função IIf</span><span class="sxs-lookup"><span data-stu-id="f7ce3-141">Using the IIf Function</span></span>  
 <span data-ttu-id="f7ce3-142">Se a operação de exemplo não for comum ou se a operação se aplicar somente a uma consulta MDX, a função [IIF](/sql/mdx/iif-mdx) poderá ser usada com a `RollupChildren` função para fornecer o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-142">If the example operation is not commonplace or if the operation applies only to one MDX query, the [IIf](/sql/mdx/iif-mdx) function can be used with the `RollupChildren` function to provide the same result.</span></span> <span data-ttu-id="f7ce3-143">A consulta MDX a seguir apresenta o mesmo resultado que o exemplo MDX anterior, mas sem reordenar para usar uma propriedade de membro personalizado:</span><span class="sxs-lookup"><span data-stu-id="f7ce3-143">The following MDX query provides the same result as the earlier MDX example, but does so without resorting to the use of a custom member property:</span></span>  
  
```  
RollupChildren([Net Sales], IIf([Net Sales].CurrentMember.Properties("UNARY_OPERATOR") = "-", "~", [Net Sales].CurrentMember.Properties("UNARY_OPERATOR))) * 1.1  
```  
  
 <span data-ttu-id="f7ce3-144">A instrução MDX analisa o operador unário do membro filho.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-144">The MDX statement examines the unary operator of the child member.</span></span> <span data-ttu-id="f7ce3-145">Se ele for usado em uma subtração (como no caso dos membros de lucros interno e de exportação), a função `IIf` substituirá o operador unário til (~).</span><span class="sxs-lookup"><span data-stu-id="f7ce3-145">If the unary operator is used for subtraction (as in the case with the domestic and foreign returns members), the `IIf` function substitutes the tilde (~) unary operator.</span></span> <span data-ttu-id="f7ce3-146">Caso contrário, a função `IIf` utilizará o operador unário do membro filho.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-146">Otherwise, the `IIf` function uses the unary operator of the child member.</span></span> <span data-ttu-id="f7ce3-147">Por fim, o total acumulado retornado é então multiplicado por 1,1 para apresentar o valor estimado de vendas brutas internas e exportações.</span><span class="sxs-lookup"><span data-stu-id="f7ce3-147">Finally, the returned rollup total is then multiplied by 1.1 to provide the domestic and foreign gross sales forecast value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ce3-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f7ce3-148">See Also</span></span>  
 [<span data-ttu-id="f7ce3-149">Manipulando dados &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f7ce3-149">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
