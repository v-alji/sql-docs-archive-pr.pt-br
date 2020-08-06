---
title: RIGHT (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RIGHT function
ms.assetid: 83e70e75-4be5-4783-a8cf-032f82afe16e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2584ee33ecbf0436c4e3dc6e92b957e60ae396ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681022"
---
# <a name="right-ssis-expression"></a><span data-ttu-id="2ea0c-102">RIGHT (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="2ea0c-102">RIGHT (SSIS Expression)</span></span>
  <span data-ttu-id="2ea0c-103">Retorna o número especificado de caracteres da parte mais à direita da expressão character especificada.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-103">Returns the specified number of characters from the rightmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ea0c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2ea0c-104">Syntax</span></span>  
  
```  
  
RIGHT(character_expression,integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="2ea0c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2ea0c-105">Arguments</span></span>  
 <span data-ttu-id="2ea0c-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="2ea0c-106">*character_expression*</span></span>  
 <span data-ttu-id="2ea0c-107">É uma expressão de caractere da qual extrair caracteres.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="2ea0c-108">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="2ea0c-108">*integer_expression*</span></span>  
 <span data-ttu-id="2ea0c-109">É uma expressão de inteiro que indica o número de caracteres retornados.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2ea0c-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="2ea0c-110">Result Types</span></span>  
 <span data-ttu-id="2ea0c-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="2ea0c-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ea0c-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="2ea0c-112">Remarks</span></span>  
 <span data-ttu-id="2ea0c-113">Se *integer_expression* for maior que o comprimento de *character_expression*, a função retornará *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-113">If *integer_expression* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="2ea0c-114">Se *integer_expression* for zero, a função retornará uma cadeia de comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-114">If *integer_expression* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="2ea0c-115">Se *integer_expression* for um número negativo, a função retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-115">If *integer_expression* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="2ea0c-116">O argumento *integer_expression* pode assumir variáveis e colunas.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-116">The *integer_expression* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="2ea0c-117">RIGHT só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-117">RIGHT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="2ea0c-118">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes que RIGHT execute sua operação.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RIGHT performs its operation.</span></span> <span data-ttu-id="2ea0c-119">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="2ea0c-120">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2ea0c-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="2ea0c-121">RIGHT retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-121">RIGHT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2ea0c-122">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="2ea0c-122">Expression Examples</span></span>  
 <span data-ttu-id="2ea0c-123">O exemplo a seguir usa um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-123">The following example uses a string literal.</span></span> <span data-ttu-id="2ea0c-124">O resultado de retorno é `"Bike"`.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-124">The return result is `"Bike"`.</span></span>  
  
```  
RIGHT("Mountain Bike", 4)  
```  
  
 <span data-ttu-id="2ea0c-125">Este exemplo retorna o número dos caracteres na extrema direita que são especificados na variável `Times` , da coluna `Name` .</span><span class="sxs-lookup"><span data-stu-id="2ea0c-125">The following example returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="2ea0c-126">Se `Name` for `Touring Front Wheel` e `Times` for 5, o resultado de retorno será `"Wheel"`.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-126">If `Name` is `Touring Front Wheel` and `Times` is 5, the return result is `"Wheel"`.</span></span>  
  
```  
RIGHT(Name, @Times)  
```  
  
 <span data-ttu-id="2ea0c-127">Este exemplo a seguir retorna o número dos caracteres na extrema direita que são especificados na variável `Times` , da coluna `Name` .</span><span class="sxs-lookup"><span data-stu-id="2ea0c-127">The following example also returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="2ea0c-128">`Times` tem um tipo de dados não inteiro e a expressão inclui uma conversão explícita para o tipo de dados DT_I2.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-128">`Times` has a noninteger data type and the expression includes an explicit cast to the DT_I2 data type.</span></span> <span data-ttu-id="2ea0c-129">Se `Name` for `Touring Front Wheel` e `Times` for `4.32`, o resultado de retorno será `"heel"` porque a função RIGHT converterá o valor de 4.32 para 4, e então retornará os quatro caracteres na extrema direita.</span><span class="sxs-lookup"><span data-stu-id="2ea0c-129">If `Name` is `Touring Front Wheel` and `Times` is `4.32`, the return result is `"heel"` because the RIGHT function converts the value of 4.32 to 4, and then returns the rightmost four characters.</span></span>  
  
```  
RIGHT(Name, (DT_I2)@Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ea0c-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ea0c-130">See Also</span></span>  
 <span data-ttu-id="2ea0c-131">[LEFT &#40;Expressão SSIS&#41;](left-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2ea0c-131">[LEFT &#40;SSIS Expression&#41;](left-ssis-expression.md) </span></span>  
 [<span data-ttu-id="2ea0c-132">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2ea0c-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
