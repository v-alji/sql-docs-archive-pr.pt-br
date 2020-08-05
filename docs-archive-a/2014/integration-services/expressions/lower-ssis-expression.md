---
title: LOWER (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting uppercase to lowercase
- LOWER function
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: 109328e1-5604-40ff-895e-f2e7c13fff41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 180be8f3cfb5a15eb0fcd6ddd3d63b09fe874af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573204"
---
# <a name="lower-ssis-expression"></a><span data-ttu-id="0c6f7-102">LOWER (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="0c6f7-102">LOWER (SSIS Expression)</span></span>
  <span data-ttu-id="0c6f7-103">Retorna uma expressão character depois de converter caracteres maiúsculos em minúsculos.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-103">Returns a character expression after converting uppercase characters to lowercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c6f7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c6f7-104">Syntax</span></span>  
  
```  
  
LOWER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c6f7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0c6f7-105">Arguments</span></span>  
 <span data-ttu-id="0c6f7-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="0c6f7-106">*character_expression*</span></span>  
 <span data-ttu-id="0c6f7-107">É uma expressão de caractere para converter para caracteres minúsculos.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-107">Is a character expression to convert to lowercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0c6f7-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="0c6f7-108">Result Types</span></span>  
 <span data-ttu-id="0c6f7-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="0c6f7-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c6f7-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c6f7-110">Remarks</span></span>  
 <span data-ttu-id="0c6f7-111">LOWER só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-111">LOWER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="0c6f7-112">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes de LOWER executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LOWER performs its operation.</span></span> <span data-ttu-id="0c6f7-113">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="0c6f7-114">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0c6f7-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="0c6f7-115">LOWER retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-115">LOWER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0c6f7-116">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="0c6f7-116">Expression Examples</span></span>  
 <span data-ttu-id="0c6f7-117">Este exemplo converte um literal de cadeia de caracteres para caracteres minúsculos.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-117">This example converts a string literal to lowercase characters.</span></span> <span data-ttu-id="0c6f7-118">O resultado de retorno é "Nova Iorque".</span><span class="sxs-lookup"><span data-stu-id="0c6f7-118">The return result is "new york".</span></span>  
  
```  
LOWER("New York")  
```  
  
 <span data-ttu-id="0c6f7-119">Este exemplo converte todos os caracteres da coluna de entrada **Color** , exceto o primeiro caractere, para caracteres minúsculos.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-119">This example converts all characters from the **Color** input column, except the first character, to lowercase characters.</span></span> <span data-ttu-id="0c6f7-120">Se Color for AMARELO, o resultado de retorno será "Amarelo".</span><span class="sxs-lookup"><span data-stu-id="0c6f7-120">If Color is YELLOW, the return result is "Yellow".</span></span> <span data-ttu-id="0c6f7-121">Para obter mais informações, consulte [SUBSTRING &#40;Expressão do SSIS&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0c6f7-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
LOWER(SUBSTRING(Color, 2, 15))  
```  
  
 <span data-ttu-id="0c6f7-122">Este exemplo converte o valor na variável **CityName** para caracteres minúsculos.</span><span class="sxs-lookup"><span data-stu-id="0c6f7-122">This example converts the value in the **CityName** variable to lowercase characters.</span></span>  
  
```  
LOWER(@CityName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c6f7-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c6f7-123">See Also</span></span>  
 <span data-ttu-id="0c6f7-124">[UPPER &#40;Expressão do SSIS&#41;](upper-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="0c6f7-124">[UPPER &#40;SSIS Expression&#41;](upper-ssis-expression.md) </span></span>  
 [<span data-ttu-id="0c6f7-125">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0c6f7-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
