---
title: '! (Não Lógico) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logical Not (!)
- '! (logical Not)'
ms.assetid: d5c4d1e1-7be4-4d25-bcd9-5b6ddb53b3b3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bbf313930575e864f1556952425567fca96db15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573205"
---
# <a name="-logical-not-ssis-expression"></a><span data-ttu-id="0abd8-103">!</span><span class="sxs-lookup"><span data-stu-id="0abd8-103">!</span></span> <span data-ttu-id="0abd8-104">(Não lógico) (Expressão do SSIS)</span><span class="sxs-lookup"><span data-stu-id="0abd8-104">(Logical Not) (SSIS Expression)</span></span>
  <span data-ttu-id="0abd8-105">Nega um operando booliano.</span><span class="sxs-lookup"><span data-stu-id="0abd8-105">Negates a Boolean operand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0abd8-106">O operador !</span><span class="sxs-lookup"><span data-stu-id="0abd8-106">The !</span></span> <span data-ttu-id="0abd8-107">não pode ser usado em conjunto com outros operadores.</span><span class="sxs-lookup"><span data-stu-id="0abd8-107">operator cannot be used in conjunction with other operators.</span></span> <span data-ttu-id="0abd8-108">Por exemplo, você não pode combinar os operadores !</span><span class="sxs-lookup"><span data-stu-id="0abd8-108">For example, you cannot combine the !</span></span> <span data-ttu-id="0abd8-109">e os operadores > no operador</span><span class="sxs-lookup"><span data-stu-id="0abd8-109">and the > operators into the !>.</span></span> <span data-ttu-id="0abd8-110">!>.</span><span class="sxs-lookup"><span data-stu-id="0abd8-110">operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0abd8-111">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0abd8-111">Syntax</span></span>  
  
```  
  
!boolean_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0abd8-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0abd8-112">Arguments</span></span>  
 <span data-ttu-id="0abd8-113">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="0abd8-113">*boolean_expression*</span></span>  
 <span data-ttu-id="0abd8-114">É qualquer expressão válida avaliada como um Booliano.</span><span class="sxs-lookup"><span data-stu-id="0abd8-114">Is any valid expression that evaluates to a Boolean.</span></span> <span data-ttu-id="0abd8-115">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0abd8-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0abd8-116">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="0abd8-116">Result Types</span></span>  
 <span data-ttu-id="0abd8-117">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="0abd8-117">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0abd8-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="0abd8-118">Remarks</span></span>  
 <span data-ttu-id="0abd8-119">A tabela a seguir mostra o resultado da operação</span><span class="sxs-lookup"><span data-stu-id="0abd8-119">The following table shows the result of the !</span></span> <span data-ttu-id="0abd8-120">operação.</span><span class="sxs-lookup"><span data-stu-id="0abd8-120">operation.</span></span>  
  
|<span data-ttu-id="0abd8-121">Expressão booliana original</span><span class="sxs-lookup"><span data-stu-id="0abd8-121">Original Boolean expression</span></span>|<span data-ttu-id="0abd8-122">Depois de aplicar o</span><span class="sxs-lookup"><span data-stu-id="0abd8-122">After applying the !</span></span> <span data-ttu-id="0abd8-123">operador</span><span class="sxs-lookup"><span data-stu-id="0abd8-123">operator</span></span>|  
|---------------------------------|------------------------------------|  
|<span data-ttu-id="0abd8-124">TRUE</span><span class="sxs-lookup"><span data-stu-id="0abd8-124">TRUE</span></span>|<span data-ttu-id="0abd8-125">FALSE</span><span class="sxs-lookup"><span data-stu-id="0abd8-125">FALSE</span></span>|  
|<span data-ttu-id="0abd8-126">NULO</span><span class="sxs-lookup"><span data-stu-id="0abd8-126">NULL</span></span>|<span data-ttu-id="0abd8-127">NULO</span><span class="sxs-lookup"><span data-stu-id="0abd8-127">NULL</span></span>|  
|<span data-ttu-id="0abd8-128">FALSE</span><span class="sxs-lookup"><span data-stu-id="0abd8-128">FALSE</span></span>|<span data-ttu-id="0abd8-129">TRUE</span><span class="sxs-lookup"><span data-stu-id="0abd8-129">TRUE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="0abd8-130">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="0abd8-130">Expression Examples</span></span>  
 <span data-ttu-id="0abd8-131">Este exemplo será avaliado como FALSE se o valor da coluna **Color** for "vermelho".</span><span class="sxs-lookup"><span data-stu-id="0abd8-131">This example evaluates to FALSE if the **Color** column value is "red".</span></span>  
  
```  
!(Color == "red")  
```  
  
 <span data-ttu-id="0abd8-132">Esse exemplo será avaliado como TRUE se o valor da variável **MonthNumber** for o mesmo que o inteiro que representa o mês atual.</span><span class="sxs-lookup"><span data-stu-id="0abd8-132">This example evaluates to TRUE if the value of the **MonthNumber** variable is the same as the integer that represents the current month.</span></span> <span data-ttu-id="0abd8-133">Para obter mais informações, consulte [MONTH &#40;Expressão SSIS&#41;](month-ssis-expression.md) e [GETDATE &#40;Expressão SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0abd8-133">For more information, see [MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) and [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
!(@MonthNumber != MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="0abd8-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0abd8-134">See Also</span></span>  
 <span data-ttu-id="0abd8-135">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="0abd8-135">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="0abd8-136">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0abd8-136">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
