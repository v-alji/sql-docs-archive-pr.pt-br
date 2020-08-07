---
title: '&amp; (AND bit a bit) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- AND, bitwise AND
- '& (bitwise AND)'
- bitwise AND (&)
ms.assetid: 06d2958e-66a5-44d8-8bc4-56209ebe1ff2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbf3c8ffcef079e25c82478947bc3b92a6b4be93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575975"
---
# <a name="amp-bitwise-and-ssis-expression"></a><span data-ttu-id="f4e8d-102">&amp; (AND bit a bit) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="f4e8d-102">&amp; (Bitwise AND) (SSIS Expression)</span></span>
  <span data-ttu-id="f4e8d-103">Executa uma operação AND de bit a bit de dois valores de inteiro.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-103">Performs a bitwise AND operation of two integer values.</span></span> <span data-ttu-id="f4e8d-104">Compara cada bit de seu primeiro operando com o bit correspondente de seu segundo operando.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="f4e8d-105">Se ambos os bits forem 1, o bit de resultado correspondente será definido como 1.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-105">If both bits are 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="f4e8d-106">Caso contrário, o bit de resultado correspondente é definido como zero (0).</span><span class="sxs-lookup"><span data-stu-id="f4e8d-106">Otherwise, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="f4e8d-107">Ambas as condições devem ser um tipo de dados inteiro assinado ou ambas as condições devem ser um tipo de dados inteiro não assinado.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-107">Both conditions must be a signed integer type or both conditions must be an unsigned integer type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4e8d-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f4e8d-108">Syntax</span></span>  
  
```  
  
integer_expression1 & integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f4e8d-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f4e8d-109">Arguments</span></span>  
 <span data-ttu-id="f4e8d-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="f4e8d-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="f4e8d-111">É qualquer expressão válida de um tipo de dados inteiro assinado ou não assinado.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="f4e8d-112">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f4e8d-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f4e8d-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="f4e8d-113">Result Types</span></span>  
 <span data-ttu-id="f4e8d-114">Determinado por tipos de dados dos dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="f4e8d-115">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f4e8d-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4e8d-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="f4e8d-116">Remarks</span></span>  
 <span data-ttu-id="f4e8d-117">Se qualquer condição for nula, o resultado de expressão será nulo.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f4e8d-118">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="f4e8d-118">Expression Examples</span></span>  
 <span data-ttu-id="f4e8d-119">Este exemplo executa uma operação AND de bit a bit entre as colunas **NumberA** e **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-119">This example performs a bitwise AND operation between the columns **NumberA** and **NumberB**.</span></span> <span data-ttu-id="f4e8d-120">**NumberA** contém 3 (0000011) e a coluna **NumberB** contém 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="f4e8d-120">**NumberA** contains 3 (0000011) and column **NumberB** contains 7 (00000111).</span></span>  
  
```  
NumberA & NumberB  
```  
  
 <span data-ttu-id="f4e8d-121">A expressão é avaliada como 3 (00000011).</span><span class="sxs-lookup"><span data-stu-id="f4e8d-121">The expression evaluates to 3 (00000011).</span></span>  
  
 <span data-ttu-id="f4e8d-122">00000011</span><span class="sxs-lookup"><span data-stu-id="f4e8d-122">00000011</span></span>  
  
 <span data-ttu-id="f4e8d-123">00000111</span><span class="sxs-lookup"><span data-stu-id="f4e8d-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="f4e8d-124">00000011</span><span class="sxs-lookup"><span data-stu-id="f4e8d-124">00000011</span></span>  
  
 <span data-ttu-id="f4e8d-125">Este exemplo executa uma operação AND de bit a bit entre as colunas **ReorderPoint** e **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="f4e8d-125">This example performs a bitwise AND operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint & SafetyStockLevel  
```  
  
 <span data-ttu-id="f4e8d-126">Se **ReorderPoint** for 10 e **SafetyStockLevel** for 8, a expressão será avaliada como 8 (00001000).</span><span class="sxs-lookup"><span data-stu-id="f4e8d-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 8 (00001000).</span></span>  
  
 <span data-ttu-id="f4e8d-127">00001010</span><span class="sxs-lookup"><span data-stu-id="f4e8d-127">00001010</span></span>  
  
 <span data-ttu-id="f4e8d-128">00001000</span><span class="sxs-lookup"><span data-stu-id="f4e8d-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="f4e8d-129">00001000</span><span class="sxs-lookup"><span data-stu-id="f4e8d-129">00001000</span></span>  
  
 <span data-ttu-id="f4e8d-130">Este exemplo executa uma operação AND de bit a bit entre dois inteiros.</span><span class="sxs-lookup"><span data-stu-id="f4e8d-130">This example performs a bitwise AND operation between two integers.</span></span>  
  
```  
3 & 5   
```  
  
 <span data-ttu-id="f4e8d-131">A expressão é avaliada como 1 (00000001).</span><span class="sxs-lookup"><span data-stu-id="f4e8d-131">The expression evaluates to 1(00000001).</span></span>  
  
 <span data-ttu-id="f4e8d-132">00000011</span><span class="sxs-lookup"><span data-stu-id="f4e8d-132">00000011</span></span>  
  
 <span data-ttu-id="f4e8d-133">00000101</span><span class="sxs-lookup"><span data-stu-id="f4e8d-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="f4e8d-134">00000001</span><span class="sxs-lookup"><span data-stu-id="f4e8d-134">00000001</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4e8d-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4e8d-135">See Also</span></span>  
 <span data-ttu-id="f4e8d-136">[&& &#40;AND lógico&#41; &#40;Expressão SSIS&#41;](logical-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f4e8d-136">[&& &#40;Logical AND&#41; &#40;SSIS Expression&#41;](logical-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="f4e8d-137">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="f4e8d-137">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="f4e8d-138">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f4e8d-138">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
