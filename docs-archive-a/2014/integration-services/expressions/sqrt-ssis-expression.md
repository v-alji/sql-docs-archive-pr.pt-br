---
title: SQRT (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQRT function
- square root of given expression
ms.assetid: 54a75389-c501-4e22-87b8-905f66d6a3a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9efa3f8da2e5280692aa65a25610211aba2fa40f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681012"
---
# <a name="sqrt-ssis-expression"></a><span data-ttu-id="8fb18-102">SQRT (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="8fb18-102">SQRT (SSIS Expression)</span></span>
  <span data-ttu-id="8fb18-103">Retorna a raiz quadrada de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="8fb18-103">Returns the square root of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fb18-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8fb18-104">Syntax</span></span>  
  
```  
  
SQRT(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="8fb18-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8fb18-105">Arguments</span></span>  
 <span data-ttu-id="8fb18-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="8fb18-106">*numeric_expression*</span></span>  
 <span data-ttu-id="8fb18-107">É uma expressão numérica de qualquer tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="8fb18-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="8fb18-108">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="8fb18-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8fb18-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="8fb18-109">Result Types</span></span>  
 <span data-ttu-id="8fb18-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="8fb18-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fb18-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="8fb18-111">Remarks</span></span>  
 <span data-ttu-id="8fb18-112">SQRT retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="8fb18-112">SQRT returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="8fb18-113">SQRT falhará se o argumento for um valor negativo.</span><span class="sxs-lookup"><span data-stu-id="8fb18-113">SQRT fails if the argument is a negative value.</span></span>  
  
 <span data-ttu-id="8fb18-114">O argumento é convertido para o tipo de dados de DT_R8 antes da operação de raiz quadrada.</span><span class="sxs-lookup"><span data-stu-id="8fb18-114">The argument is cast to the DT_R8 data type before the square root operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="8fb18-115">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="8fb18-115">Expression Examples</span></span>  
 <span data-ttu-id="8fb18-116">Este exemplo retorna a raiz quadrada de um literal numérico.</span><span class="sxs-lookup"><span data-stu-id="8fb18-116">This example returns the square root of a numeric literal.</span></span> <span data-ttu-id="8fb18-117">O resultado de retorno é 12.</span><span class="sxs-lookup"><span data-stu-id="8fb18-117">The return result is 12.</span></span>  
  
```  
SQRT(144)  
```  
  
 <span data-ttu-id="8fb18-118">Este exemplo retorna a raiz quadrada de uma expressão, o resultado da subtração de valores nas colunas **Value1** e **Value2** .</span><span class="sxs-lookup"><span data-stu-id="8fb18-118">This example returns the square root of an expression, the result of subtracting values in the **Value1** and **Value2** columns.</span></span>  
  
```  
SQRT(Value1 - Value2)  
```  
  
 <span data-ttu-id="8fb18-119">Este exemplo retorna o comprimento do terceiro lado de um triângulo direito, aplicando a função SQUARE a duas variáveis e calculando, em seguida, a raiz quadrada da soma.</span><span class="sxs-lookup"><span data-stu-id="8fb18-119">This example returns the length of the third side of a right triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="8fb18-120">Se **Side1** contiver 3 e **Side2** contiver 4, a função SQRT retornará 5.</span><span class="sxs-lookup"><span data-stu-id="8fb18-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="8fb18-121">Em expressões, nomes de variável incluem sempre o prefixo \@.</span><span class="sxs-lookup"><span data-stu-id="8fb18-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb18-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8fb18-122">See Also</span></span>  
 [<span data-ttu-id="8fb18-123">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8fb18-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
