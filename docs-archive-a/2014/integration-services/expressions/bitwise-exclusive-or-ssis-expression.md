---
title: ^ (OR exclusivo bit a bit) (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ^ (bitwise exclusive OR operator)
- bitwise exclusive OR (^)
ms.assetid: 6ac53cab-29c4-4835-9f87-371b058b2f38
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d86c3d810e9e5572af93c97f82c2275db2c979b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575976"
---
# <a name="-bitwise-exclusive-or-ssis-expression"></a><span data-ttu-id="b870b-102">^ (OR exclusivo de bit a bit) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="b870b-102">^ (Bitwise Exclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="b870b-103">Executa uma operação OR de bit a bit exclusiva de dois valores inteiros.</span><span class="sxs-lookup"><span data-stu-id="b870b-103">Performs a bitwise exclusive OR operation of two integer values.</span></span> <span data-ttu-id="b870b-104">Compara cada bit de seu primeiro operando com o bit correspondente de seu segundo operando.</span><span class="sxs-lookup"><span data-stu-id="b870b-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="b870b-105">Se um bit for 0 e o outro bit for 1, o bit de resultado correspondente será definido como 1.</span><span class="sxs-lookup"><span data-stu-id="b870b-105">If one bit is 0 and the other bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="b870b-106">Se ambos os bits forem 0 ou ambos os bits forem 1, o bit de resultado correspondente será definido como 0.</span><span class="sxs-lookup"><span data-stu-id="b870b-106">If both bits are 0 or both bits are 1, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="b870b-107">Ambas as condições devem ser um tipo de dados inteiro assinado ou ambas as condições devem ser um tipo de dados inteiro não assinado.</span><span class="sxs-lookup"><span data-stu-id="b870b-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b870b-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b870b-108">Syntax</span></span>  
  
```  
  
integer_expression1 ^ integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b870b-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b870b-109">Arguments</span></span>  
 <span data-ttu-id="b870b-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="b870b-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="b870b-111">É qualquer expressão válida de um tipo de dados inteiro assinado ou não assinado.</span><span class="sxs-lookup"><span data-stu-id="b870b-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="b870b-112">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b870b-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b870b-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="b870b-113">Result Types</span></span>  
 <span data-ttu-id="b870b-114">Determinado por tipos de dados dos dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="b870b-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="b870b-115">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b870b-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b870b-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="b870b-116">Remarks</span></span>  
 <span data-ttu-id="b870b-117">Se qualquer condição for nula, o resultado de expressão será nulo.</span><span class="sxs-lookup"><span data-stu-id="b870b-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b870b-118">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="b870b-118">Expression Examples</span></span>  
 <span data-ttu-id="b870b-119">Este exemplo executa uma operação OR de bit a bit exclusiva entre as variáveis **NumberA** e **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="b870b-119">This example performs a bitwise exclusive OR operation between variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="b870b-120">**NumberA** contém 3 (00000011) e **NumberB** contém 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="b870b-120">**NumberA** contains 3 (00000011) and **NumberB** contains 7 (00000111).</span></span>  
  
```  
@NumberA ^ @NumberB  
```  
  
 <span data-ttu-id="b870b-121">A expressão é avaliada como 4 (00000100).</span><span class="sxs-lookup"><span data-stu-id="b870b-121">The expression evaluates to 4 (00000100).</span></span>  
  
 <span data-ttu-id="b870b-122">00000011</span><span class="sxs-lookup"><span data-stu-id="b870b-122">00000011</span></span>  
  
 <span data-ttu-id="b870b-123">00000111</span><span class="sxs-lookup"><span data-stu-id="b870b-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="b870b-124">00000100</span><span class="sxs-lookup"><span data-stu-id="b870b-124">00000100</span></span>  
  
 <span data-ttu-id="b870b-125">Este exemplo executa uma operação OR de bit a bit exclusiva entre as colunas **ReorderPoint** e **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="b870b-125">This example performs a bitwise exclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint ^ SafetyStockLevel  
```  
  
 <span data-ttu-id="b870b-126">Se **ReorderPoint** for 10 e **SafetyStockLevel** for 8, a expressão será avaliada como 2 (00000010).</span><span class="sxs-lookup"><span data-stu-id="b870b-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 2 (00000010).</span></span>  
  
 <span data-ttu-id="b870b-127">00001010</span><span class="sxs-lookup"><span data-stu-id="b870b-127">00001010</span></span>  
  
 <span data-ttu-id="b870b-128">00001000</span><span class="sxs-lookup"><span data-stu-id="b870b-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="b870b-129">00000010</span><span class="sxs-lookup"><span data-stu-id="b870b-129">00000010</span></span>  
  
 <span data-ttu-id="b870b-130">Este exemplo executa uma operação OR de bit a bit exclusiva entre dois inteiros.</span><span class="sxs-lookup"><span data-stu-id="b870b-130">This example performs a bitwise exclusive OR operation between two integers.</span></span>  
  
```  
3 ^ 5   
```  
  
 <span data-ttu-id="b870b-131">A expressão é avaliada como 6 (00000110).</span><span class="sxs-lookup"><span data-stu-id="b870b-131">The expression evaluates to 6 (00000110).</span></span>  
  
 <span data-ttu-id="b870b-132">00000011</span><span class="sxs-lookup"><span data-stu-id="b870b-132">00000011</span></span>  
  
 <span data-ttu-id="b870b-133">00000101</span><span class="sxs-lookup"><span data-stu-id="b870b-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="b870b-134">00000110</span><span class="sxs-lookup"><span data-stu-id="b870b-134">00000110</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b870b-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b870b-135">See Also</span></span>  
 <span data-ttu-id="b870b-136">[&#124;&#124; &#40;OR lógica&#41; &#40;Expressão SSIS&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b870b-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="b870b-137">[&#124; &#40;OR inclusivo de bit a bit&#41; &#40;Expressão SSIS&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b870b-137">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="b870b-138">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="b870b-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="b870b-139">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b870b-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
