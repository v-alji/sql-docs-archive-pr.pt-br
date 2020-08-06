---
title: SUBSTRING (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SUBSTRING function
- part of expression returned [Integration Services]
ms.assetid: 3a46748a-f5f8-4a6c-9108-673666754068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba53676bc6d13ed34892f48fca3b70372cb30604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681005"
---
# <a name="substring-ssis-expression"></a><span data-ttu-id="90404-102">SUBSTRING (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="90404-102">SUBSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="90404-103">Retorna a parte de uma expressão de caractere que inicia na posição especificada e tem o comprimento especificado.</span><span class="sxs-lookup"><span data-stu-id="90404-103">Returns the part of a character expression that starts at the specified position and has the specified length.</span></span> <span data-ttu-id="90404-104">O parâmetro *position* e o parâmetro *length* devem ser avaliados como inteiros.</span><span class="sxs-lookup"><span data-stu-id="90404-104">The *position* parameter and the *length* parameter must evaluate to integers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90404-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="90404-105">Syntax</span></span>  
  
```  
  
SUBSTRING(character_expression, position, length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="90404-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="90404-106">Arguments</span></span>  
 <span data-ttu-id="90404-107">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="90404-107">*character_expression*</span></span>  
 <span data-ttu-id="90404-108">É uma expressão de caractere da qual extrair caracteres.</span><span class="sxs-lookup"><span data-stu-id="90404-108">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="90404-109">*position*</span><span class="sxs-lookup"><span data-stu-id="90404-109">*position*</span></span>  
 <span data-ttu-id="90404-110">É um inteiro que especifica onde a subcadeia de caracteres começa.</span><span class="sxs-lookup"><span data-stu-id="90404-110">Is an integer that specifies where the substring begins.</span></span>  
  
 <span data-ttu-id="90404-111">*length*</span><span class="sxs-lookup"><span data-stu-id="90404-111">*length*</span></span>  
 <span data-ttu-id="90404-112">É um inteiro que especifica o comprimento da subcadeia de caracteres como o número de caracteres.</span><span class="sxs-lookup"><span data-stu-id="90404-112">Is an integer that specifies the length of the substring as number of characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="90404-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="90404-113">Result Types</span></span>  
 <span data-ttu-id="90404-114">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="90404-114">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90404-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="90404-115">Remarks</span></span>  
 <span data-ttu-id="90404-116">SUBSTRING usa um único índice.</span><span class="sxs-lookup"><span data-stu-id="90404-116">SUBSTRING uses a one-based index.</span></span> <span data-ttu-id="90404-117">Se *position* for 1, a subcadeia de caracteres começará com o primeiro caractere em *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="90404-117">If *position* is 1, the substring begins with the first character in *character_expression*.</span></span>  
  
 <span data-ttu-id="90404-118">SUBSTRING só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="90404-118">SUBSTRING works only with the DT_WSTR data type.</span></span> <span data-ttu-id="90404-119">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes que SUBSTRING execute sua operação.</span><span class="sxs-lookup"><span data-stu-id="90404-119">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before SUBSTRING performs its operation.</span></span> <span data-ttu-id="90404-120">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="90404-120">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="90404-121">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="90404-121">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="90404-122">SUBSTRING retorna um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="90404-122">SUBSTRING returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="90404-123">Todos os argumentos na expressão podem usar variáveis e colunas.</span><span class="sxs-lookup"><span data-stu-id="90404-123">All arguments in the expression can use variables and columns.</span></span>  
  
 <span data-ttu-id="90404-124">O argumento *length* pode exceder o comprimento da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="90404-124">The *length* argument can exceed the length of the string.</span></span> <span data-ttu-id="90404-125">Naquele caso, a função retorna o restante da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="90404-125">In that case, the function returns the remainder of the string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="90404-126">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="90404-126">Expression Examples</span></span>  
 <span data-ttu-id="90404-127">Este exemplo retorna dois caracteres, começando com o caractere 4, de uma literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="90404-127">This example returns two characters, beginning with character 4, from a string literal.</span></span> <span data-ttu-id="90404-128">O resultado de retorno é "ph".</span><span class="sxs-lookup"><span data-stu-id="90404-128">The return result is "ph".</span></span>  
  
```  
SUBSTRING("elephant",4,2)  
```  
  
 <span data-ttu-id="90404-129">Este exemplo retorna o restante de uma literal de cadeia de caracteres, começando no quarto caractere.</span><span class="sxs-lookup"><span data-stu-id="90404-129">This example returns the remainder of a string literal, beginning at the fourth character.</span></span> <span data-ttu-id="90404-130">O resultado de retorno é "phant".</span><span class="sxs-lookup"><span data-stu-id="90404-130">The return result is "phant".</span></span> <span data-ttu-id="90404-131">Isso não é um erro para o argumento *length* exceder o comprimento da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="90404-131">It is not an error for the *length* argument to exceed the length of the string.</span></span>  
  
```  
SUBSTRING ("elephant",4,50)  
```  
  
 <span data-ttu-id="90404-132">Este exemplo retorna a primeira letra da coluna **MiddleName** .</span><span class="sxs-lookup"><span data-stu-id="90404-132">This example returns the first letter from the **MiddleName** column.</span></span>  
  
```  
SUBSTRING(MiddleName,1,1)  
```  
  
 <span data-ttu-id="90404-133">Este exemplo usa variáveis nos argumentos *position* e *length* .</span><span class="sxs-lookup"><span data-stu-id="90404-133">This example uses variables in the *position* and *length* arguments.</span></span> <span data-ttu-id="90404-134">Se **Start** for 1 e **Length** for 5, a função retornará os primeiros cinco caracteres na coluna **Name** .</span><span class="sxs-lookup"><span data-stu-id="90404-134">If **Start** is 1 and **Length** is 5, the function returns the first five characters in the **Name** column.</span></span>  
  
```  
SUBSTRING(Name,@Start,@Length)  
```  
  
 <span data-ttu-id="90404-135">Este exemplo retorna os últimos quatro caracteres da variável **PostalCode** começando no sexto caractere.</span><span class="sxs-lookup"><span data-stu-id="90404-135">This example returns the last four characters from the **PostalCode** variable beginning at the sixth character.</span></span>  
  
```  
SUBSTRING (@PostalCode,6,4)  
```  
  
 <span data-ttu-id="90404-136">Este exemplo retorna uma cadeia de caracteres de comprimento zero de uma literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="90404-136">This example returns a zero-length string from a string literal.</span></span>  
  
```  
SUBSTRING ("Redmond",4,0)  
```  
  
## <a name="see-also"></a><span data-ttu-id="90404-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90404-137">See Also</span></span>  
 [<span data-ttu-id="90404-138">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="90404-138">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
