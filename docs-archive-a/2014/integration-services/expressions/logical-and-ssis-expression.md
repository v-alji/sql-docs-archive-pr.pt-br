---
title: '&amp;&amp; (AND lógico) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '&& (logical AND)'
- AND, logical AND
- logical AND (&&)
ms.assetid: a8cb3517-d5d1-4861-9f04-905c719185ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8d973d7d4e86f88f7ae88c820ed4e4a5c1ce526f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679450"
---
# <a name="ampamp-logical-and-ssis-expression"></a><span data-ttu-id="f76c3-102">&amp;&amp; (AND lógico) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="f76c3-102">&amp;&amp; (Logical AND) (SSIS Expression)</span></span>
  <span data-ttu-id="f76c3-103">Executa uma operação AND lógica.</span><span class="sxs-lookup"><span data-stu-id="f76c3-103">Performs a logical AND operation.</span></span> <span data-ttu-id="f76c3-104">A expressão será avaliada como TRUE se todas as condições forem TRUE.</span><span class="sxs-lookup"><span data-stu-id="f76c3-104">The expression evaluates to TRUE if all conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f76c3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f76c3-105">Syntax</span></span>  
  
```  
  
boolean_expression1 && boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="f76c3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f76c3-106">Arguments</span></span>  
 <span data-ttu-id="f76c3-107">*boolean _expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="f76c3-107">*boolean _expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="f76c3-108">É qualquer expressão válida que é avaliada como TRUE, FALSE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="f76c3-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f76c3-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="f76c3-109">Result Types</span></span>  
 <span data-ttu-id="f76c3-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="f76c3-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f76c3-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="f76c3-111">Remarks</span></span>  
 <span data-ttu-id="f76c3-112">A tabela a seguir mostra o resultado do operador &&.</span><span class="sxs-lookup"><span data-stu-id="f76c3-112">The following table shows the result of the && operator.</span></span>  
  
|<span data-ttu-id="f76c3-113">Result</span><span class="sxs-lookup"><span data-stu-id="f76c3-113">Result</span></span>|<span data-ttu-id="f76c3-114">Expression</span><span class="sxs-lookup"><span data-stu-id="f76c3-114">Expression</span></span>|<span data-ttu-id="f76c3-115">Expression</span><span class="sxs-lookup"><span data-stu-id="f76c3-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="f76c3-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="f76c3-116">TRUE</span></span>|<span data-ttu-id="f76c3-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="f76c3-117">TRUE</span></span>|<span data-ttu-id="f76c3-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="f76c3-118">TRUE</span></span>|  
|<span data-ttu-id="f76c3-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="f76c3-119">FALSE</span></span>|<span data-ttu-id="f76c3-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="f76c3-120">TRUE</span></span>|<span data-ttu-id="f76c3-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="f76c3-121">FALSE</span></span>|  
|<span data-ttu-id="f76c3-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="f76c3-122">FALSE</span></span>|<span data-ttu-id="f76c3-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="f76c3-123">FALSE</span></span>|<span data-ttu-id="f76c3-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="f76c3-124">FALSE</span></span>|  
|<span data-ttu-id="f76c3-125">NULO</span><span class="sxs-lookup"><span data-stu-id="f76c3-125">NULL</span></span>|<span data-ttu-id="f76c3-126">NULO</span><span class="sxs-lookup"><span data-stu-id="f76c3-126">NULL</span></span>|<span data-ttu-id="f76c3-127">NULO</span><span class="sxs-lookup"><span data-stu-id="f76c3-127">NULL</span></span>|  
|<span data-ttu-id="f76c3-128">NULO</span><span class="sxs-lookup"><span data-stu-id="f76c3-128">NULL</span></span>|<span data-ttu-id="f76c3-129">NULO</span><span class="sxs-lookup"><span data-stu-id="f76c3-129">NULL</span></span>|<span data-ttu-id="f76c3-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="f76c3-130">TRUE</span></span>|  
|<span data-ttu-id="f76c3-131">FALSE</span><span class="sxs-lookup"><span data-stu-id="f76c3-131">FALSE</span></span>|<span data-ttu-id="f76c3-132">NULO</span><span class="sxs-lookup"><span data-stu-id="f76c3-132">NULL</span></span>|<span data-ttu-id="f76c3-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="f76c3-133">FALSE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="f76c3-134">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="f76c3-134">Expression Examples</span></span>  
 <span data-ttu-id="f76c3-135">Este exemplo usa **StandardCost** e as colunas **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="f76c3-135">This example uses the **StandardCost** and the **ListPrice** columns.</span></span> <span data-ttu-id="f76c3-136">O exemplo avaliará como TRUE se o valor da coluna **StandardCost** for menor que 300 e a coluna **ListPrice** for maior que 500.</span><span class="sxs-lookup"><span data-stu-id="f76c3-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 and the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 && ListPrice > 500  
```  
  
 <span data-ttu-id="f76c3-137">Este exemplo usa as variáveis **SPrice** e **LPrice** em vez de literais.</span><span class="sxs-lookup"><span data-stu-id="f76c3-137">This example uses the variables **SPrice** and **LPrice** instead of literals.</span></span>  
  
```  
StandardCost < @SPrice && ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="f76c3-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f76c3-138">See Also</span></span>  
 <span data-ttu-id="f76c3-139">[& &#40;AND bit a bit&#41; &#40;Expressão SSIS&#41;](bitwise-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f76c3-139">[& &#40;Bitwise AND&#41; &#40;SSIS Expression&#41;](bitwise-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="f76c3-140">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="f76c3-140">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="f76c3-141">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f76c3-141">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
