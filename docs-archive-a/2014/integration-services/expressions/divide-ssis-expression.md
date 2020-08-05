---
title: Dividir (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- / (divide)
- divide operator (/)
ms.assetid: 5bde9223-872d-443e-8a27-57735e1d8f3d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4541cd4601047770d1bf361077b1c474219e8833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570765"
---
# <a name="divide-ssis-expression"></a><span data-ttu-id="f94c4-102">Divide (SSIS Expression)</span><span class="sxs-lookup"><span data-stu-id="f94c4-102">Divide (SSIS Expression)</span></span>
  <span data-ttu-id="f94c4-103">Divide a primeira expressão numérica pela segunda.</span><span class="sxs-lookup"><span data-stu-id="f94c4-103">Divides the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f94c4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f94c4-104">Syntax</span></span>  
  
```  
  
dividend / divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f94c4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f94c4-105">Arguments</span></span>  
 <span data-ttu-id="f94c4-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="f94c4-106">*dividend*</span></span>  
 <span data-ttu-id="f94c4-107">É a expressão numérica a ser dividida.</span><span class="sxs-lookup"><span data-stu-id="f94c4-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="f94c4-108">*dividend* pode ser qualquer expressão numérica válida.</span><span class="sxs-lookup"><span data-stu-id="f94c4-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="f94c4-109">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f94c4-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="f94c4-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="f94c4-110">*divisor*</span></span>  
 <span data-ttu-id="f94c4-111">É a expressão numérica pela qual dividir o dividendo.</span><span class="sxs-lookup"><span data-stu-id="f94c4-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="f94c4-112">*divisor* pode ser qualquer expressão numérica com exceção de zero.</span><span class="sxs-lookup"><span data-stu-id="f94c4-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f94c4-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="f94c4-113">Result Types</span></span>  
 <span data-ttu-id="f94c4-114">Determinado por tipos de dados dos dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="f94c4-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="f94c4-115">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f94c4-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f94c4-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="f94c4-116">Remarks</span></span>  
 <span data-ttu-id="f94c4-117">Se qualquer operando for nulo, o resultado será nulo.</span><span class="sxs-lookup"><span data-stu-id="f94c4-117">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="f94c4-118">Dividir por zero não é legal.</span><span class="sxs-lookup"><span data-stu-id="f94c4-118">Dividing by zero is not legal.</span></span> <span data-ttu-id="f94c4-119">Dependendo de como a subexpressão *divisor* é avaliada, um do seguintes erros acontece:</span><span class="sxs-lookup"><span data-stu-id="f94c4-119">Depending on how the *divisor* subexpression is evaluated, one of following errors occurs:</span></span>  
  
-   <span data-ttu-id="f94c4-120">Se a subexpressão *divisor* que é avaliada como zero for uma constante, o erro é exibido no tempo de design, fazendo com que a expressão falhe na validação.</span><span class="sxs-lookup"><span data-stu-id="f94c4-120">If the *divisor* subexpression that evaluates to zero is a constant, the error appears at design time, causing the expression to fail validation.</span></span>  
  
-   <span data-ttu-id="f94c4-121">Se a subexpressão *divisor* avaliada como zero contiver variáveis, mas nenhuma coluna de entrada, o componente ao qual a expressão pertence falhará na validação de pré-execução que ocorre antes de o pacote ser executado.</span><span class="sxs-lookup"><span data-stu-id="f94c4-121">If the *divisor* subexpression that evaluates to zero contains variables, but no input columns, the component to which the expression belongs fails the pre-execution validation that occurs before the package runs.</span></span>  
  
-   <span data-ttu-id="f94c4-122">Se a subexpressão *divisor* avaliada como zero contiver as colunas de entrada, o erro será exibido no tempo de execução e será tratado de acordo com as regras do fluxo de erros do componente de fluxo de regras.</span><span class="sxs-lookup"><span data-stu-id="f94c4-122">If the *divisor* subexpression that evaluates to zero contains input columns, the error appears at run time and is handled according to the error flow rules of the data flow component.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f94c4-123">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="f94c4-123">Expression Examples</span></span>  
 <span data-ttu-id="f94c4-124">Este exemplo divide dois literais numéricos.</span><span class="sxs-lookup"><span data-stu-id="f94c4-124">This example divides two numeric literals.</span></span>  
  
```  
25 / 5  
```  
  
 <span data-ttu-id="f94c4-125">Este exemplo divide valores na coluna **ListPrice** pelos valores na coluna **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="f94c4-125">This example divides values in the **ListPrice** column by values in the **StandardCost** column.</span></span>  
  
```  
ListPrice / StandardCost  
```  
  
## <a name="see-also"></a><span data-ttu-id="f94c4-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f94c4-126">See Also</span></span>  
 <span data-ttu-id="f94c4-127">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="f94c4-127">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="f94c4-128">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f94c4-128">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
