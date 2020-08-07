---
title: POWER (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- POWER function
ms.assetid: db48ae65-bfa6-4db1-8d3c-d0d4f8a399bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1f5742f482ae52620ec11d95b84cb3d06199fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574784"
---
# <a name="power-ssis-expression"></a><span data-ttu-id="b4f0b-102">POWER (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="b4f0b-102">POWER (SSIS Expression)</span></span>
  <span data-ttu-id="b4f0b-103">Retorna o resultado da elevação de uma expressão numérica a uma potência.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-103">Returns the result of raising a numeric expression to a power.</span></span> <span data-ttu-id="b4f0b-104">O parâmetro de potência deve ser avaliado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-104">The power parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f0b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b4f0b-105">Syntax</span></span>  
  
```  
  
POWER(numeric_expression,power)  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4f0b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b4f0b-106">Arguments</span></span>  
 <span data-ttu-id="b4f0b-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="b4f0b-107">*numeric_expression*</span></span>  
 <span data-ttu-id="b4f0b-108">É uma expressão numérica válida.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-108">Is a valid numeric expression.</span></span>  
  
 <span data-ttu-id="b4f0b-109">*power*</span><span class="sxs-lookup"><span data-stu-id="b4f0b-109">*power*</span></span>  
 <span data-ttu-id="b4f0b-110">É uma expressão numérica válida.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-110">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b4f0b-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="b4f0b-111">Result Types</span></span>  
 <span data-ttu-id="b4f0b-112">DT_R8</span><span class="sxs-lookup"><span data-stu-id="b4f0b-112">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4f0b-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="b4f0b-113">Remarks</span></span>  
 <span data-ttu-id="b4f0b-114">Os argumentos *numeric_expression* e *power* são convertidos para o tipo de dados de DT_R8 antes de a potência ser calculada.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-114">The *numeric_expression* and *power* arguments are cast to the DT_R8 data type before the power is computed.</span></span> <span data-ttu-id="b4f0b-115">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b4f0b-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="b4f0b-116">Se *numeric_expression* for avaliado como zero e *power* for negativo, o avaliador de expressão retornará um erro e definirá o resultado de retorno como nulo.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-116">If *numeric_expression* evaluates to zero and *power* is negative, the expression evaluator returns an error and sets the return result to null.</span></span>  
  
 <span data-ttu-id="b4f0b-117">Se *numeric_expression* ou *power* forem avaliados como resultados indeterminados, o resultado de retorno será nulo.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-117">If *numeric_expression* or *power* evaluate to indeterminate results, the return result is null.</span></span>  
  
 <span data-ttu-id="b4f0b-118">O argumento *power* pode ser uma fração.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-118">The *power* argument can be a fraction.</span></span> <span data-ttu-id="b4f0b-119">Por exemplo, você pode usar o valor 0.5 como a potência.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-119">For example, you can use the value 0.5 as the power.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b4f0b-120">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="b4f0b-120">Expression Examples</span></span>  
 <span data-ttu-id="b4f0b-121">Esse exemplo usa um literal numérico.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-121">This example uses a numeric literal.</span></span> <span data-ttu-id="b4f0b-122">A função eleva 4 à potência de 3 e retorna 64.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-122">The function raises 4 to the power of 3 and returns 64.</span></span>  
  
```  
POWER(4,3)  
```  
  
 <span data-ttu-id="b4f0b-123">Este exemplo usa a coluna **Length** e a variável **DimensionCount** .</span><span class="sxs-lookup"><span data-stu-id="b4f0b-123">This example uses the **Length** column and the **DimensionCount** variable.</span></span> <span data-ttu-id="b4f0b-124">Se **Length** for 8, e **DimensionCount** for 2, o resultado de retorno será 64.</span><span class="sxs-lookup"><span data-stu-id="b4f0b-124">If **Length** is 8, and **DimensionCount** is 2, the return result is 64.</span></span>  
  
```  
POWER(Length, @DimensionCount)   
```  
  
## <a name="see-also"></a><span data-ttu-id="b4f0b-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4f0b-125">See Also</span></span>  
 [<span data-ttu-id="b4f0b-126">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b4f0b-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
