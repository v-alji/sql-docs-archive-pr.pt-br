---
title: SQUARE (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQUARE
- square values
ms.assetid: cecf1bb2-3d55-40a6-9688-ed67bcc150b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 09955e708aae707a88aa7821d2a72651a3a44d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681010"
---
# <a name="square-ssis-expression"></a><span data-ttu-id="7dfa9-102">SQUARE (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="7dfa9-102">SQUARE (SSIS Expression)</span></span>
  <span data-ttu-id="7dfa9-103">Retorna o quadrado de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-103">Returns the square of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfa9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7dfa9-104">Syntax</span></span>  
  
```  
  
SQUARE(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7dfa9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7dfa9-105">Arguments</span></span>  
 <span data-ttu-id="7dfa9-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="7dfa9-106">*numeric_expression*</span></span>  
 <span data-ttu-id="7dfa9-107">É uma expressão numérica de qualquer tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="7dfa9-108">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7dfa9-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7dfa9-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="7dfa9-109">Result Types</span></span>  
 <span data-ttu-id="7dfa9-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="7dfa9-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dfa9-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="7dfa9-111">Remarks</span></span>  
 <span data-ttu-id="7dfa9-112">SQUARE retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-112">SQUARE returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="7dfa9-113">O argumento é convertido para o tipo de dados de DT_R8 antes da operação de raiz quadrada.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-113">The argument is cast to the DT_R8 data type before the square operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7dfa9-114">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="7dfa9-114">Expression Examples</span></span>  
 <span data-ttu-id="7dfa9-115">Este exemplo retorna o quadrado de 12.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-115">This example returns the square of 12.</span></span> <span data-ttu-id="7dfa9-116">O resultado retornado é 144.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-116">The return result is 144.</span></span>  
  
```  
SQUARE(12)  
```  
  
 <span data-ttu-id="7dfa9-117">Este exemplo retorna o quadrado do resultado da subtração de valores em duas colunas.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-117">This example returns the square of the result of subtracting values in two columns.</span></span> <span data-ttu-id="7dfa9-118">Se **Value1** contiver 12 e **Value2** contiver 4, a função SQUARE retornará 64.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-118">If **Value1** contains 12 and **Value2** contains 4, the SQUARE function returns 64.</span></span>  
  
```  
SQUARE(Value1 - Value2)  
```  
  
 <span data-ttu-id="7dfa9-119">Este exemplo retorna o comprimento do terceiro lado de um triângulo de ângulo direito, aplicando a função SQUARE a duas variáveis e calculando, em seguida, a raiz quadrada da soma.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-119">This example returns the length of the third side of a right angle triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="7dfa9-120">Se **Side1** contiver 3 e **Side2** contiver 4, a função SQRT retornará 5.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="7dfa9-121">Em expressões, nomes de variável incluem sempre o prefixo \@.</span><span class="sxs-lookup"><span data-stu-id="7dfa9-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfa9-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7dfa9-122">See Also</span></span>  
 [<span data-ttu-id="7dfa9-123">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7dfa9-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
