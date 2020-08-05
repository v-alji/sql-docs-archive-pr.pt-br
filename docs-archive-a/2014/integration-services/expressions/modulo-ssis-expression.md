---
title: (Módulo) (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '% (modulo operator)'
- remainder of division operation
- modulo operator (%)
ms.assetid: e2920821-2f5b-4c76-8db8-8b9eddf4606f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e23152fca9c9f2c7c3ac11490a56b03d1a1f9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573203"
---
# <a name="modulo-ssis-expression"></a><span data-ttu-id="59640-102">(Módulo) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="59640-102">(Modulo) (SSIS Expression)</span></span>
  <span data-ttu-id="59640-103">Fornece o resto inteiro após dividir a primeira expressão numérica pela segunda.</span><span class="sxs-lookup"><span data-stu-id="59640-103">Provides the integer remainder after dividing the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59640-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="59640-104">Syntax</span></span>  
  
```  
  
dividend % divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="59640-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="59640-105">Arguments</span></span>  
 <span data-ttu-id="59640-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="59640-106">*dividend*</span></span>  
 <span data-ttu-id="59640-107">É a expressão numérica a ser dividida.</span><span class="sxs-lookup"><span data-stu-id="59640-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="59640-108">*dividend* pode ser qualquer expressão numérica válida.</span><span class="sxs-lookup"><span data-stu-id="59640-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="59640-109">Para obter mais informações, consulte [Tipos de Dados do Integration Services](../data-flow/integration-services-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="59640-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md)</span></span>  
  
 <span data-ttu-id="59640-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="59640-110">*divisor*</span></span>  
 <span data-ttu-id="59640-111">É a expressão numérica pela qual dividir o dividendo.</span><span class="sxs-lookup"><span data-stu-id="59640-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="59640-112">*divisor* pode ser qualquer expressão numérica com exceção de zero.</span><span class="sxs-lookup"><span data-stu-id="59640-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="59640-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="59640-113">Result Types</span></span>  
 <span data-ttu-id="59640-114">Determinado por tipos de dados dos dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="59640-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="59640-115">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="59640-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59640-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="59640-116">Remarks</span></span>  
 <span data-ttu-id="59640-117">Ambas as expressões devem ser avaliadas como tipos de dados inteiro assinados ou não assinados.</span><span class="sxs-lookup"><span data-stu-id="59640-117">Both expressions must evaluate to signed or unsigned integer data types.</span></span>  
  
 <span data-ttu-id="59640-118">Se qualquer operando for nulo, o resultado será nulo.</span><span class="sxs-lookup"><span data-stu-id="59640-118">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="59640-119">Módulo zero não é válido.</span><span class="sxs-lookup"><span data-stu-id="59640-119">Modulo zero is not legal.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="59640-120">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="59640-120">Expression Examples</span></span>  
 <span data-ttu-id="59640-121">Esse exemplo calcula o módulo de dois literals numéricos.</span><span class="sxs-lookup"><span data-stu-id="59640-121">This example computes the modulus from two numeric literals.</span></span> <span data-ttu-id="59640-122">O resultado é 3.</span><span class="sxs-lookup"><span data-stu-id="59640-122">The result is 3.</span></span>  
  
```  
42 % 13  
```  
  
 <span data-ttu-id="59640-123">Esse exemplo calcula o módulo da coluna **SalesQuota** e um literal numérico.</span><span class="sxs-lookup"><span data-stu-id="59640-123">This example computes the modulus from the **SalesQuota** column and a numeric literal.</span></span>  
  
```  
SalesQuota % 12  
```  
  
 <span data-ttu-id="59640-124">Esse exemplo calcula o módulo de duas variáveis numéricas **Sales$** e **Month**.</span><span class="sxs-lookup"><span data-stu-id="59640-124">This example computes the modulus from two numeric variables **Sales$** and **Month**.</span></span> <span data-ttu-id="59640-125">A variável **Sales$** deve estar entre colchetes porque o nome inclui o caractere $.</span><span class="sxs-lookup"><span data-stu-id="59640-125">The variable **Sales$** must be enclosed in brackets because the name includes the $ character.</span></span> <span data-ttu-id="59640-126">Para obter mais informações, consulte [Identificadores &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="59640-126">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
@[Sales$] % @Month  
```  
  
 <span data-ttu-id="59640-127">Esse exemplo usa o operador de módulo para determinar se o valor da variável **Value** é par ou ímpar e se usa o operador condicional para retornar uma cadeia que descreve o resultado.</span><span class="sxs-lookup"><span data-stu-id="59640-127">This example uses the modulo operator to determine if the value of the **Value** variable is even or odd, and uses the conditional operator to return a string that describes the result.</span></span> <span data-ttu-id="59640-128">Para obter mais informações, consulte [? : &#40;Condicional&#41; &#40;Expressão SSIS&#41;](conditional-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="59640-128">For more information, see [? : &#40;Conditional&#41; &#40;SSIS Expression&#41;](conditional-ssis-expression.md).</span></span>  
  
```  
@Value % 2 == 0? "even":"odd"  
```  
  
## <a name="see-also"></a><span data-ttu-id="59640-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="59640-129">See Also</span></span>  
 <span data-ttu-id="59640-130">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="59640-130">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="59640-131">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="59640-131">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
