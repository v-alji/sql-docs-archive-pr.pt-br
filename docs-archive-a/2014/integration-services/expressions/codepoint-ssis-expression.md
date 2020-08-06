---
title: CODEPOINT (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CODEPOINT function
- leftmost character of expression
ms.assetid: 0783d05e-7f35-42fb-a2c4-9621c46effd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf05cc0838763ba9e22707af57892133d449da07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569563"
---
# <a name="codepoint-ssis-expression"></a><span data-ttu-id="a0673-102">CODEPOINT (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="a0673-102">CODEPOINT (SSIS Expression)</span></span>
  <span data-ttu-id="a0673-103">Retorna o ponto de código Unicode do caractere da extrema esquerda de uma expressão de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a0673-103">Returns the Unicode code point of the leftmost character of a character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0673-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a0673-104">Syntax</span></span>  
  
```  
  
CODEPOINT(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="a0673-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a0673-105">Arguments</span></span>  
 <span data-ttu-id="a0673-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="a0673-106">*character_expression*</span></span>  
 <span data-ttu-id="a0673-107">É uma expressão de caracteres cujo caractere da extrema esquerda será avaliado.</span><span class="sxs-lookup"><span data-stu-id="a0673-107">Is a character expression whose leftmost character will be evaluated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a0673-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="a0673-108">Result Types</span></span>  
 <span data-ttu-id="a0673-109">DT_UI2</span><span class="sxs-lookup"><span data-stu-id="a0673-109">DT_UI2</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0673-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="a0673-110">Remarks</span></span>  
 <span data-ttu-id="a0673-111">*character_expression* deve ter o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="a0673-111">*character_expression* must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="a0673-112">CODEPOINT retornará um resultado nulo se *character_expression* for nulo ou uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="a0673-112">CODEPOINT returns a null result if *character_expression* is null or an empty string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="a0673-113">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="a0673-113">Expression Examples</span></span>  
 <span data-ttu-id="a0673-114">Este exemplo usa um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a0673-114">This example uses a string literal.</span></span> <span data-ttu-id="a0673-115">O resultado de retorno é 77, o ponto de código Unicode para M.</span><span class="sxs-lookup"><span data-stu-id="a0673-115">The return result is 77, the Unicode code point for M.</span></span>  
  
```  
CODEPOINT("Mountain Bike")  
```  
  
 <span data-ttu-id="a0673-116">Este exemplo usa uma variável.</span><span class="sxs-lookup"><span data-stu-id="a0673-116">This example uses a variable.</span></span> <span data-ttu-id="a0673-117">Se **Name** for Roda Dianteira de Passeio, o resultado de retorno será 84, o ponto de código de Unicode para T.</span><span class="sxs-lookup"><span data-stu-id="a0673-117">If **Name** is Touring Front Wheel, the return result is 84, the Unicode code point for T.</span></span>  
  
```  
CODEPOINT(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0673-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0673-118">See Also</span></span>  
 [<span data-ttu-id="a0673-119">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="a0673-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
