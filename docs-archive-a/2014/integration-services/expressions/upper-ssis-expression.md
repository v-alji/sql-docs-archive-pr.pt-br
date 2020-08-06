---
title: UPPER (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- UPPER function
- converting lowercase to uppercase
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: d33985f7-1048-4023-83e4-274090acda78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181e231d735a8e98cd2bce10c692e35668a686f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680992"
---
# <a name="upper-ssis-expression"></a><span data-ttu-id="96d73-102">UPPER (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="96d73-102">UPPER (SSIS Expression)</span></span>
  <span data-ttu-id="96d73-103">Retorna uma expressão de caractere depois de converter caracteres minúsculos em maiúsculos.</span><span class="sxs-lookup"><span data-stu-id="96d73-103">Returns a character expression after converting lowercase characters to uppercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d73-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="96d73-104">Syntax</span></span>  
  
```  
  
UPPER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="96d73-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="96d73-105">Arguments</span></span>  
 <span data-ttu-id="96d73-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="96d73-106">*character_expression*</span></span>  
 <span data-ttu-id="96d73-107">É uma expressão de caractere para converter para caracteres maiúsculos.</span><span class="sxs-lookup"><span data-stu-id="96d73-107">Is a character expression to convert to uppercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="96d73-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="96d73-108">Result Types</span></span>  
 <span data-ttu-id="96d73-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="96d73-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96d73-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="96d73-110">Remarks</span></span>  
 <span data-ttu-id="96d73-111">UPPER só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="96d73-111">UPPER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="96d73-112">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes de UPPER executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="96d73-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before UPPER performs its operation.</span></span> <span data-ttu-id="96d73-113">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="96d73-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="96d73-114">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="96d73-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="96d73-115">UPPER retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="96d73-115">UPPER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="96d73-116">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="96d73-116">Expression Examples</span></span>  
 <span data-ttu-id="96d73-117">Este exemplo converte um literal de cadeia de caracteres para caracteres maiúsculos.</span><span class="sxs-lookup"><span data-stu-id="96d73-117">This example converts a string literal to uppercase characters.</span></span> <span data-ttu-id="96d73-118">O resultado de retorno é "Hello".</span><span class="sxs-lookup"><span data-stu-id="96d73-118">The return result is "HELLO".</span></span>  
  
```  
UPPER("hello")  
```  
  
 <span data-ttu-id="96d73-119">Este exemplo converte o primeiro caractere na coluna **FirstName** para um caractere maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="96d73-119">This example converts the first character in the **FirstName** column to an uppercase character.</span></span> <span data-ttu-id="96d73-120">Se **FirstName** for anna, o resultado de retorno será "A".</span><span class="sxs-lookup"><span data-stu-id="96d73-120">If **FirstName** is anna, the return result is "A".</span></span> <span data-ttu-id="96d73-121">Para obter mais informações, consulte [SUBSTRING &#40;Expressão do SSIS&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="96d73-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
UPPER(SUBSTRING(FirstName, 1, 1))  
```  
  
 <span data-ttu-id="96d73-122">Este exemplo converte o valor na variável **PostalCode** escrever em caracteres de letra maiúscula.</span><span class="sxs-lookup"><span data-stu-id="96d73-122">This example converts the value in the **PostalCode** variable to uppercase characters.</span></span> <span data-ttu-id="96d73-123">Se **PostalCode** for k4b1s2, o resultado de retorno será "K4B1S2".</span><span class="sxs-lookup"><span data-stu-id="96d73-123">If **PostalCode** is k4b1s2, the return result is "K4B1S2".</span></span>  
  
```  
UPPER(@PostalCode)  
```  
  
## <a name="see-also"></a><span data-ttu-id="96d73-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96d73-124">See Also</span></span>  
 <span data-ttu-id="96d73-125">[LOWER &#40;Expressão SSIS&#41;](lower-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="96d73-125">[LOWER &#40;SSIS Expression&#41;](lower-ssis-expression.md) </span></span>  
 [<span data-ttu-id="96d73-126">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="96d73-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
