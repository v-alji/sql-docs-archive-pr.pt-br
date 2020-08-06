---
title: LN (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LN function
- natural logarithm of expression [Integration Services]
ms.assetid: 55d7b657-b5fd-4753-9c81-54ed7575e720
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c06d6e246cfa51f8e84eb93ab7eb73eab40c392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575967"
---
# <a name="ln-ssis-expression"></a><span data-ttu-id="e075f-102">LN (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="e075f-102">LN (SSIS Expression)</span></span>
  <span data-ttu-id="e075f-103">Retorna o logaritmo natural de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="e075f-103">Returns the natural logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e075f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e075f-104">Syntax</span></span>  
  
```  
  
LN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e075f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e075f-105">Arguments</span></span>  
 <span data-ttu-id="e075f-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="e075f-106">*numeric_expression*</span></span>  
 <span data-ttu-id="e075f-107">É uma expressão numérica não negativa, diferente de zero válida.</span><span class="sxs-lookup"><span data-stu-id="e075f-107">Is a valid non-zero and non-negative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e075f-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="e075f-108">Result Types</span></span>  
 <span data-ttu-id="e075f-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="e075f-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e075f-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="e075f-110">Remarks</span></span>  
 <span data-ttu-id="e075f-111">A expressão numérica é convertida para o tipo de dados DT_R8 antes de o logaritmo ser computado.</span><span class="sxs-lookup"><span data-stu-id="e075f-111">The numeric expression is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="e075f-112">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e075f-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="e075f-113">Se *numeric_expression* for avaliado como zero ou um valor negativo, o resultado de retorno será nulo.</span><span class="sxs-lookup"><span data-stu-id="e075f-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e075f-114">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="e075f-114">Expression Examples</span></span>  
 <span data-ttu-id="e075f-115">Esse exemplo usa um literal numérico.</span><span class="sxs-lookup"><span data-stu-id="e075f-115">This example uses a numeric literal.</span></span> <span data-ttu-id="e075f-116">A função retorna o valor 3.737766961828337.</span><span class="sxs-lookup"><span data-stu-id="e075f-116">The function returns the value 3.737766961828337.</span></span>  
  
```  
LN(42)  
```  
  
 <span data-ttu-id="e075f-117">Esse exemplo usa a coluna **Length**.</span><span class="sxs-lookup"><span data-stu-id="e075f-117">This example uses the column **Length**.</span></span> <span data-ttu-id="e075f-118">Se o valor da coluna for 53.99, a função retornará 3.9887988442302.</span><span class="sxs-lookup"><span data-stu-id="e075f-118">If the column value is 53.99, the function returns 3.9887988442302.</span></span>  
  
```  
LN(Length)   
```  
  
 <span data-ttu-id="e075f-119">Esse exemplo usa a variável **Length**.</span><span class="sxs-lookup"><span data-stu-id="e075f-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="e075f-120">A variável deve ser um tipo de dados numérico ou a expressão deve incluir uma conversão explícita para um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="e075f-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric data type.</span></span> <span data-ttu-id="e075f-121">Se **Length** for 234.567, a função retornará 5.45774126708797.</span><span class="sxs-lookup"><span data-stu-id="e075f-121">If **Length** is 234.567, the function returns 5.45774126708797.</span></span>  
  
```  
LN(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="e075f-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e075f-122">See Also</span></span>  
 <span data-ttu-id="e075f-123">[LOG &#40;Expressão SSIS&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e075f-123">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="e075f-124">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e075f-124">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
