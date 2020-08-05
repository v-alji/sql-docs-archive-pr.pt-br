---
title: LEN (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LEN function
- number of characters
ms.assetid: d961398b-e4d0-4936-be17-8f4c5882a640
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8863864168295a3a9a924df588312ee65b6f7fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572601"
---
# <a name="len-ssis-expression"></a><span data-ttu-id="33edd-102">LEN (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="33edd-102">LEN (SSIS Expression)</span></span>
  <span data-ttu-id="33edd-103">Retorna o número de caracteres em uma expressão character.</span><span class="sxs-lookup"><span data-stu-id="33edd-103">Returns the number of characters in a character expression.</span></span> <span data-ttu-id="33edd-104">Se a cadeia de caracteres incluir espaços em branco à esquerda e à direita, a função os incluirá na contagem.</span><span class="sxs-lookup"><span data-stu-id="33edd-104">If the string includes leading and trailing blanks, the function includes them in the count.</span></span> <span data-ttu-id="33edd-105">LEN retorna valores idênticos para a mesma cadeia de caracteres de byte único e duplo.</span><span class="sxs-lookup"><span data-stu-id="33edd-105">LEN returns identical values for the same string of single and double byte characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33edd-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="33edd-106">Syntax</span></span>  
  
```  
  
LEN(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="33edd-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="33edd-107">Arguments</span></span>  
 <span data-ttu-id="33edd-108">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="33edd-108">*character_expression*</span></span>  
 <span data-ttu-id="33edd-109">É a expressão a ser avaliada.</span><span class="sxs-lookup"><span data-stu-id="33edd-109">Is the expression to evaluate.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="33edd-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="33edd-110">Result Types</span></span>  
 <span data-ttu-id="33edd-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="33edd-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33edd-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="33edd-112">Remarks</span></span>  
 <span data-ttu-id="33edd-113">O argumento *character_expression* pode ser um tipo de dados DT_WSTR, DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="33edd-113">The *character_expression* argument can be a DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="33edd-114">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="33edd-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="33edd-115">Se *character_expression* for um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR, ele será implicitamente convertido para o tipo de dados DT_WSTR antes de LEN executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="33edd-115">If *character_expression* is a string literal or a data column with the DT_STR data type, it is implicitly cast to the DT_WSTR data type before LEN performs its operation.</span></span> <span data-ttu-id="33edd-116">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="33edd-116">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="33edd-117">Para obter mais informações, consulte [Cast &#40;Expressão do SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="33edd-117">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="33edd-118">Se o argumento transmitido para a função LEN tiver um tipo de dados BLOB (Binary Large Object Block), como DT_TEXT, DT_NTEXT ou DT_IMAGE, a função retornará uma contagem de bytes.</span><span class="sxs-lookup"><span data-stu-id="33edd-118">If the argument passed to the LEN function has a Binary Large Object Block (BLOB) data type, such as DT_TEXT, DT_NTEXT, or DT_IMAGE, the function returns a byte count.</span></span>  
  
 <span data-ttu-id="33edd-119">LEN retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="33edd-119">LEN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="33edd-120">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="33edd-120">Expression Examples</span></span>  
 <span data-ttu-id="33edd-121">Este exemplo retorna o comprimento de uma literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="33edd-121">This example returns the length of a string literal.</span></span> <span data-ttu-id="33edd-122">O resultado de retorno é 12.</span><span class="sxs-lookup"><span data-stu-id="33edd-122">The return result is 12.</span></span>  
  
```  
LEN("Ball Bearing")  
```  
  
 <span data-ttu-id="33edd-123">Este exemplo retorna a diferença entre o comprimento de valores nas colunas **FirstName** e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="33edd-123">This example returns the difference between the length of values in the **FirstName** and **LastName** columns.</span></span>  
  
```  
LEN(FirstName) - LEN(LastName)  
```  
  
 <span data-ttu-id="33edd-124">Retorna o comprimento de um nome do computador que usa a variável de Sistema **MachineName**.</span><span class="sxs-lookup"><span data-stu-id="33edd-124">Returns the length of a computer name using the System variable **MachineName**.</span></span>  
  
```  
LEN(@MachineName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="33edd-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33edd-125">See Also</span></span>  
 [<span data-ttu-id="33edd-126">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="33edd-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
