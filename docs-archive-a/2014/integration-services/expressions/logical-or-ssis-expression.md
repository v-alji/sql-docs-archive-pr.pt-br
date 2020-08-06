---
title: '|| (OR lógico) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OR operator
- logical OR (||)
- '|| (logical OR)'
ms.assetid: a3c07c09-f121-4187-9617-b01adcf843c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72d4a1c7b54856675f0faa7f5f58452cb8bca450
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679451"
---
# <a name="-logical-or-ssis-expression"></a><span data-ttu-id="4e8f6-102">|| (OR lógico) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="4e8f6-102">|| (Logical OR) (SSIS Expression)</span></span>
  <span data-ttu-id="4e8f6-103">Executa uma operação OR lógica.</span><span class="sxs-lookup"><span data-stu-id="4e8f6-103">Performs a logical OR operation.</span></span> <span data-ttu-id="4e8f6-104">A expressão será avaliada como TRUE se uma ou ambas as condições forem TRUE.</span><span class="sxs-lookup"><span data-stu-id="4e8f6-104">The expression evaluates to TRUE if one or both conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e8f6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4e8f6-105">Syntax</span></span>  
  
```  
  
boolean_expression1 || boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="4e8f6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4e8f6-106">Arguments</span></span>  
 <span data-ttu-id="4e8f6-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="4e8f6-107">*boolean_expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="4e8f6-108">É qualquer expressão válida que é avaliada como TRUE, FALSE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="4e8f6-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4e8f6-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="4e8f6-109">Result Types</span></span>  
 <span data-ttu-id="4e8f6-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="4e8f6-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e8f6-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="4e8f6-111">Remarks</span></span>  
 <span data-ttu-id="4e8f6-112">A tabela a seguir mostra o resultado do operador ||.</span><span class="sxs-lookup"><span data-stu-id="4e8f6-112">The following table shows the result of the || operator.</span></span>  
  
|<span data-ttu-id="4e8f6-113">Result</span><span class="sxs-lookup"><span data-stu-id="4e8f6-113">Result</span></span>|<span data-ttu-id="4e8f6-114">Expression</span><span class="sxs-lookup"><span data-stu-id="4e8f6-114">Expression</span></span>|<span data-ttu-id="4e8f6-115">Expression</span><span class="sxs-lookup"><span data-stu-id="4e8f6-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="4e8f6-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-116">TRUE</span></span>|<span data-ttu-id="4e8f6-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-117">TRUE</span></span>|<span data-ttu-id="4e8f6-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-118">TRUE</span></span>|  
|<span data-ttu-id="4e8f6-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-119">TRUE</span></span>|<span data-ttu-id="4e8f6-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-120">TRUE</span></span>|<span data-ttu-id="4e8f6-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-121">FALSE</span></span>|  
|<span data-ttu-id="4e8f6-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-122">FALSE</span></span>|<span data-ttu-id="4e8f6-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-123">FALSE</span></span>|<span data-ttu-id="4e8f6-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-124">FALSE</span></span>|  
|<span data-ttu-id="4e8f6-125">NULO</span><span class="sxs-lookup"><span data-stu-id="4e8f6-125">NULL</span></span>|<span data-ttu-id="4e8f6-126">NULO</span><span class="sxs-lookup"><span data-stu-id="4e8f6-126">NULL</span></span>|<span data-ttu-id="4e8f6-127">NULO</span><span class="sxs-lookup"><span data-stu-id="4e8f6-127">NULL</span></span>|  
|<span data-ttu-id="4e8f6-128">TRUE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-128">TRUE</span></span>|<span data-ttu-id="4e8f6-129">NULO</span><span class="sxs-lookup"><span data-stu-id="4e8f6-129">NULL</span></span>|<span data-ttu-id="4e8f6-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-130">TRUE</span></span>|  
|<span data-ttu-id="4e8f6-131">NULO</span><span class="sxs-lookup"><span data-stu-id="4e8f6-131">NULL</span></span>|<span data-ttu-id="4e8f6-132">NULO</span><span class="sxs-lookup"><span data-stu-id="4e8f6-132">NULL</span></span>|<span data-ttu-id="4e8f6-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="4e8f6-133">FALSE</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="4e8f6-134">Exemplos de expressões SSIS</span><span class="sxs-lookup"><span data-stu-id="4e8f6-134">SSIS Expression Examples</span></span>  
 <span data-ttu-id="4e8f6-135">Este exemplo usa as colunas **StandardCost** e **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="4e8f6-135">This example uses the **StandardCost** and **ListPrice** columns.</span></span> <span data-ttu-id="4e8f6-136">O exemplo será avaliado como TRUE se o valor da coluna **StandardCost** for menor que 300 ou a coluna **ListPrice** for maior que 500.</span><span class="sxs-lookup"><span data-stu-id="4e8f6-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 or the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 || ListPrice > 500  
```  
  
 <span data-ttu-id="4e8f6-137">Este exemplo usa as variáveis **SPrice** e **LPrice** em vez de literais numéricos.</span><span class="sxs-lookup"><span data-stu-id="4e8f6-137">This example uses the variables **SPrice** and **LPrice** instead of numeric literals.</span></span>  
  
```  
StandardCost < @SPrice || ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e8f6-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e8f6-138">See Also</span></span>  
 <span data-ttu-id="4e8f6-139">[&#124; &#40;OR inclusivo de bit a bit&#41; &#40;Expressão SSIS&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4e8f6-139">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="4e8f6-140">[^ &#40;OR exclusivo de bit a bit&#41; &#40;Expressão SSIS&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4e8f6-140">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="4e8f6-141">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="4e8f6-141">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="4e8f6-142">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4e8f6-142">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
