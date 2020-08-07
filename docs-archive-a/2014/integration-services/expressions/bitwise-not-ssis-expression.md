---
title: ~ (Não bit a bit) (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- bitwise NOT (~)
- ~ (bitwise NOT)
ms.assetid: e4413ddd-0d0e-40c3-9c76-b5ce323218ec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75745a0650c1744064f2a671659879e11464514e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575968"
---
# <a name="-bitwise-not-ssis-expression"></a><span data-ttu-id="893d1-102">~ (Não de bit a bit) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="893d1-102">~ (Bitwise Not) (SSIS Expression)</span></span>
  <span data-ttu-id="893d1-103">Executa uma negação bit a bit de um inteiro.</span><span class="sxs-lookup"><span data-stu-id="893d1-103">Performs a bitwise negation of an integer.</span></span> <span data-ttu-id="893d1-104">Esse operador pode ser se aplicado a tipos de dados inteiro assinados e não assinados.</span><span class="sxs-lookup"><span data-stu-id="893d1-104">This operator can be applied to signed and unsigned integer data types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="893d1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="893d1-105">Syntax</span></span>  
  
```  
  
~integer_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="893d1-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="893d1-106">Arguments</span></span>  
 <span data-ttu-id="893d1-107">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="893d1-107">*integer_expression*</span></span>  
 <span data-ttu-id="893d1-108">É qualquer expressão válida de um tipo de dados inteiro.</span><span class="sxs-lookup"><span data-stu-id="893d1-108">Is any valid expression of an integer data type.</span></span> <span data-ttu-id="893d1-109">*integer*_*expression* é um inteiro que é transformado em um número binário para a operação bit a bit.</span><span class="sxs-lookup"><span data-stu-id="893d1-109">*integer*_*expression* is an integer that is transformed into a binary number for the bitwise operation.</span></span> <span data-ttu-id="893d1-110">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="893d1-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="893d1-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="893d1-111">Result Types</span></span>  
 <span data-ttu-id="893d1-112">Retorna o tipo de dados de *integer_expression.*</span><span class="sxs-lookup"><span data-stu-id="893d1-112">Returns the data type of *integer_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="893d1-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="893d1-113">Remarks</span></span>  
 <span data-ttu-id="893d1-114">Nenhum</span><span class="sxs-lookup"><span data-stu-id="893d1-114">None</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="893d1-115">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="893d1-115">Expression Examples</span></span>  
 <span data-ttu-id="893d1-116">Esse exemplo executa uma operação ~ (NOT) bit a bit no número 170 (0000 0000 1010 1010).</span><span class="sxs-lookup"><span data-stu-id="893d1-116">This example performs a bitwise ~ (NOT) operation on the number 170 (0000 0000 1010 1010).</span></span> <span data-ttu-id="893d1-117">O número é um inteiro assinado.</span><span class="sxs-lookup"><span data-stu-id="893d1-117">The number is a signed integer.</span></span>  
  
```  
  
~ 170  
```  
  
 <span data-ttu-id="893d1-118">A expressão é avaliada como -170 (1111111101010101).</span><span class="sxs-lookup"><span data-stu-id="893d1-118">The expression evaluates to -170 (1111111101010101).</span></span>  
  
 <span data-ttu-id="893d1-119">0000000010101010</span><span class="sxs-lookup"><span data-stu-id="893d1-119">0000000010101010</span></span>  
  
 ---------------------\-  
  
 <span data-ttu-id="893d1-120">1111111101010101</span><span class="sxs-lookup"><span data-stu-id="893d1-120">1111111101010101</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893d1-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="893d1-121">See Also</span></span>  
 <span data-ttu-id="893d1-122">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="893d1-122">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="893d1-123">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="893d1-123">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
