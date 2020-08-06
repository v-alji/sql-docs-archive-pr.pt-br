---
title: '| (OR inclusivo bit a bit) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '| (bitwise inclusive OR)'
- bitwise inclusive OR (|)
ms.assetid: 4dce9eb2-3680-4adc-81a3-816ea52cef49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 73d64886b433ffe5b4e06dc4870bbca06b2a53dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575969"
---
# <a name="-bitwise-inclusive-or-ssis-expression"></a><span data-ttu-id="b4a37-102">| (OR inclusivo de bit a bit) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="b4a37-102">| (Bitwise Inclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="b4a37-103">Executa uma operação OR de bit a bit de dois valores de inteiro.</span><span class="sxs-lookup"><span data-stu-id="b4a37-103">Performs a bitwise OR operation of two integer values.</span></span> <span data-ttu-id="b4a37-104">Compara cada bit de seu primeiro operando com o bit correspondente de seu segundo operando.</span><span class="sxs-lookup"><span data-stu-id="b4a37-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="b4a37-105">Se qualquer bit for 1, o bit de resultado correspondente será definido como 1.</span><span class="sxs-lookup"><span data-stu-id="b4a37-105">If either bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="b4a37-106">Caso contrário, o bit de resultado correspondente é definido como zero (0).</span><span class="sxs-lookup"><span data-stu-id="b4a37-106">Otherwise, the corresponding result bit is set to zero (0).</span></span>  
  
 <span data-ttu-id="b4a37-107">Ambas as condições devem ser um tipo de dados inteiro assinado ou ambas as condições devem ser um tipo de dados inteiro não assinado.</span><span class="sxs-lookup"><span data-stu-id="b4a37-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a37-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b4a37-108">Syntax</span></span>  
  
```  
  
integer_expression1 | integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4a37-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b4a37-109">Arguments</span></span>  
 <span data-ttu-id="b4a37-110">*integer_expression1, integer_ expression2*</span><span class="sxs-lookup"><span data-stu-id="b4a37-110">*integer_expression1 ,integer_ expression2*</span></span>  
 <span data-ttu-id="b4a37-111">É qualquer expressão válida de um tipo de dados inteiro assinado ou não assinado.</span><span class="sxs-lookup"><span data-stu-id="b4a37-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="b4a37-112">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4a37-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b4a37-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="b4a37-113">Result Types</span></span>  
 <span data-ttu-id="b4a37-114">Determinado por tipos de dados dos dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="b4a37-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="b4a37-115">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b4a37-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4a37-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="b4a37-116">Remarks</span></span>  
 <span data-ttu-id="b4a37-117">Se qualquer condição for nula, o resultado de expressão será nulo.</span><span class="sxs-lookup"><span data-stu-id="b4a37-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b4a37-118">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="b4a37-118">Expression Examples</span></span>  
 <span data-ttu-id="b4a37-119">Este exemplo executa uma operação OR de bit a bit inclusiva entre as variáveis **NumberA** e **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-119">This example performs a bitwise inclusive OR operation between the variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="b4a37-120">**NumberA** contém 3 (00000011) e **NumberB** contém 9 (00001001).</span><span class="sxs-lookup"><span data-stu-id="b4a37-120">**NumberA** contains 3 (00000011) and **NumberB** contains 9 (00001001).</span></span>  
  
```  
@NumberA | @NumberB  
```  
  
 <span data-ttu-id="b4a37-121">A expressão é avaliada como 11 (00001011).</span><span class="sxs-lookup"><span data-stu-id="b4a37-121">The expression evaluates to 11 (00001011).</span></span>  
  
 <span data-ttu-id="b4a37-122">00000011</span><span class="sxs-lookup"><span data-stu-id="b4a37-122">00000011</span></span>  
  
 <span data-ttu-id="b4a37-123">00001001</span><span class="sxs-lookup"><span data-stu-id="b4a37-123">00001001</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="b4a37-124">00001011</span><span class="sxs-lookup"><span data-stu-id="b4a37-124">00001011</span></span>  
  
 <span data-ttu-id="b4a37-125">Este exemplo executa uma operação OR de bit a bit inclusiva entre as colunas **ReorderPoint** e **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="b4a37-125">This example performs a bitwise inclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint | SafetyStockLevel  
```  
  
 <span data-ttu-id="b4a37-126">Se **ReorderPoint** for 10 e **SafetyStockLevel** for 8, a expressão será avaliada como 10 (00001010).</span><span class="sxs-lookup"><span data-stu-id="b4a37-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 10 (00001010).</span></span>  
  
 <span data-ttu-id="b4a37-127">00001010</span><span class="sxs-lookup"><span data-stu-id="b4a37-127">00001010</span></span>  
  
 <span data-ttu-id="b4a37-128">00001000</span><span class="sxs-lookup"><span data-stu-id="b4a37-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="b4a37-129">00001010</span><span class="sxs-lookup"><span data-stu-id="b4a37-129">00001010</span></span>  
  
 <span data-ttu-id="b4a37-130">Este exemplo executa uma operação OR de bit a bit inclusiva entre dois inteiros.</span><span class="sxs-lookup"><span data-stu-id="b4a37-130">This example performs a bitwise inclusive OR operation between two integers.</span></span>  
  
```  
3 | 5   
```  
  
 <span data-ttu-id="b4a37-131">A expressão é avaliada como 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="b4a37-131">The expression evaluates to 7 (00000111).</span></span>  
  
 <span data-ttu-id="b4a37-132">00000011</span><span class="sxs-lookup"><span data-stu-id="b4a37-132">00000011</span></span>  
  
 <span data-ttu-id="b4a37-133">00000101</span><span class="sxs-lookup"><span data-stu-id="b4a37-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="b4a37-134">00000111</span><span class="sxs-lookup"><span data-stu-id="b4a37-134">00000111</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a37-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4a37-135">See Also</span></span>  
 <span data-ttu-id="b4a37-136">[&#124;&#124; &#40;OR lógica&#41; &#40;Expressão SSIS&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b4a37-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="b4a37-137">[^ &#40;OR exclusivo de bit a bit&#41; &#40;Expressão SSIS&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b4a37-137">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="b4a37-138">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="b4a37-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="b4a37-139">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b4a37-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
