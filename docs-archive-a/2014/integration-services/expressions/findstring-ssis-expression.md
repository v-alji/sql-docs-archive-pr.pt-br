---
title: FINDSTRING (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FINDSTRING function
ms.assetid: c83cb1b1-3c52-4496-b518-4c9253b9336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72f2ff21cb179ce565e60c6550b8ecc2618a5adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573206"
---
# <a name="findstring-ssis-expression"></a><span data-ttu-id="e326d-102">FINDSTRING (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="e326d-102">FINDSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="e326d-103">Retorna o local da ocorrência especificada de uma cadeia de caracteres dentro de uma expressão de caractere.</span><span class="sxs-lookup"><span data-stu-id="e326d-103">Returns the location of the specified occurrence of a string within a character expression.</span></span> <span data-ttu-id="e326d-104">O resultado de retorno é o índice da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="e326d-104">The return result is the one-based index of the occurrence.</span></span> <span data-ttu-id="e326d-105">O parâmetro de cadeia de caracteres deve ser avaliado como uma expressão de caractere e o parâmetro de ocorrência deve ser avaliado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="e326d-105">The string parameter must evaluate to a character expression, and the occurrence parameter must evaluate to an integer.</span></span> <span data-ttu-id="e326d-106">Se a cadeia de caracteres não for localizada, o valor de retorno será 0.</span><span class="sxs-lookup"><span data-stu-id="e326d-106">If the string is not found, the return value is 0.</span></span> <span data-ttu-id="e326d-107">Se a cadeia de caracteres acontecer menos vezes que o argumento de ocorrência especifica, o valor de retorno será 0.</span><span class="sxs-lookup"><span data-stu-id="e326d-107">If the string occurs fewer times than the occurrence argument specifies, the return value is 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e326d-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e326d-108">Syntax</span></span>  
  
```  
  
FINDSTRING(character_expression, searchstring, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e326d-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e326d-109">Arguments</span></span>  
 <span data-ttu-id="e326d-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="e326d-110">*character_expression*</span></span>  
 <span data-ttu-id="e326d-111">É a cadeia de caracteres para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e326d-111">Is the character string to search in.</span></span>  
  
 <span data-ttu-id="e326d-112">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="e326d-112">*searchstring*</span></span>  
 <span data-ttu-id="e326d-113">É a cadeia de caracteres para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e326d-113">Is the character string to search for.</span></span>  
  
 <span data-ttu-id="e326d-114">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="e326d-114">*occurrence*</span></span>  
 <span data-ttu-id="e326d-115">É um inteiro com sinal ou sem sinal que especifica qual ocorrência de *searchstring* deve ser informada.</span><span class="sxs-lookup"><span data-stu-id="e326d-115">Is a signed or unsigned integer specifying which occurrence of *searchstring* to report.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e326d-116">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="e326d-116">Result Types</span></span>  
 <span data-ttu-id="e326d-117">DT_I4</span><span class="sxs-lookup"><span data-stu-id="e326d-117">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e326d-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="e326d-118">Remarks</span></span>  
 <span data-ttu-id="e326d-119">FINDSTRING funciona apenas com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e326d-119">FINDSTRING works only with the DT_WSTR data type.</span></span>  <span data-ttu-id="e326d-120">Os argumentos*character_expression* e *searchstring* , que são literais de cadeia de caracteres ou colunas de dados com o tipo de dados DT_STR, são implicitamente convertidos para o tipo de dados DT_WSTR antes de FINDSTRING executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="e326d-120">*character_expression* and *searchstring* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before FINDSTRING performs its operation.</span></span> <span data-ttu-id="e326d-121">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e326d-121">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="e326d-122">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e326d-122">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="e326d-123">FINDSTRING retornará nulo se *character_expression* ou *searchstring* forem nulos.</span><span class="sxs-lookup"><span data-stu-id="e326d-123">FINDSTRING returns null if either *character_expression* or *searchstring* are null.</span></span>  
  
 <span data-ttu-id="e326d-124">Use um valor de 1 no argumento *occurrence* para obter o índice da primeira ocorrência, 2 para a segunda ocorrência e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e326d-124">Use a value of 1 in the *occurrence* argument to get the index of the first occurrence, 2 for the second occurrence and so forth.</span></span>  
  
 <span data-ttu-id="e326d-125">A *occurrence* deve ser um inteiro com um valor maior do que 0.</span><span class="sxs-lookup"><span data-stu-id="e326d-125">The *occurrence* must be an integer with a value greater than 0.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e326d-126">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="e326d-126">Expression Examples</span></span>  
 <span data-ttu-id="e326d-127">Este exemplo usa um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e326d-127">This example uses a string literal.</span></span> <span data-ttu-id="e326d-128">Retorna o valor 11.</span><span class="sxs-lookup"><span data-stu-id="e326d-128">It returns the value 11.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 1)   
```  
  
 <span data-ttu-id="e326d-129">Este exemplo usa um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e326d-129">This example uses a string literal.</span></span> <span data-ttu-id="e326d-130">Porque a cadeia de caracteres "NY" ocorre só duas vezes, o resultado de retorno é 0.</span><span class="sxs-lookup"><span data-stu-id="e326d-130">Because the string "NY" occurs only two times, the return result is 0.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 3)   
```  
  
 <span data-ttu-id="e326d-131">Este exemplo usa a coluna **Name** .</span><span class="sxs-lookup"><span data-stu-id="e326d-131">This example uses the **Name** column.</span></span> <span data-ttu-id="e326d-132">Ele retorna o local do valor n na coluna **Name** .</span><span class="sxs-lookup"><span data-stu-id="e326d-132">It returns the location of the value n in the **Name** column.</span></span> <span data-ttu-id="e326d-133">O resultado de retorno varia, dependendo do valor em **Name**.</span><span class="sxs-lookup"><span data-stu-id="e326d-133">The return result varies depending on the value in **Name**.</span></span> <span data-ttu-id="e326d-134">Se **Name** contiver Anderson, a função retornará 8.</span><span class="sxs-lookup"><span data-stu-id="e326d-134">If **Name** contains Anderson, the function returns 8.</span></span>  
  
```  
FINDSTRING(Name,"n", 2)   
```  
  
 <span data-ttu-id="e326d-135">Este exemplo usa as colunas **Name** e **Size** .</span><span class="sxs-lookup"><span data-stu-id="e326d-135">This example uses the **Name** and **Size** columns.</span></span> <span data-ttu-id="e326d-136">Retorna o local do caractere na extrema esquerda do valor **Size** na coluna **Name** .</span><span class="sxs-lookup"><span data-stu-id="e326d-136">It returns the location of the leftmost character of the **Size** value in the **Name** column.</span></span> <span data-ttu-id="e326d-137">O resultado de retorno varia, dependendo de valores de coluna.</span><span class="sxs-lookup"><span data-stu-id="e326d-137">The return result varies depending on column values.</span></span> <span data-ttu-id="e326d-138">Se **Name** contiver Mountain,500Red,42 e **Size** contiver 42, o resultado de retorno será 17.</span><span class="sxs-lookup"><span data-stu-id="e326d-138">If **Name** contains Mountain,500Red,42 and **Size** contains 42, the return result is 17.</span></span>  
  
```  
FINDSTRING(Name,Size,1)   
```  
  
## <a name="see-also"></a><span data-ttu-id="e326d-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e326d-139">See Also</span></span>  
 <span data-ttu-id="e326d-140">[REPLACE &#40;Expressão SSIS&#41;](replace-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e326d-140">[REPLACE &#40;SSIS Expression&#41;](replace-ssis-expression.md) </span></span>  
 [<span data-ttu-id="e326d-141">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e326d-141">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
