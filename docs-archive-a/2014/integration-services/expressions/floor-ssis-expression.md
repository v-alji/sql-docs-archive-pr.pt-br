---
title: FLOOR (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- largest integer less than or equal to expression
- FLOOR function [SSIS]
ms.assetid: 168084db-badd-40f2-87b4-1f5bc45c3e24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b638c9a7215d120c562e416cdecee463f031ad2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573207"
---
# <a name="floor-ssis-expression"></a><span data-ttu-id="aadae-102">FLOOR (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="aadae-102">FLOOR (SSIS Expression)</span></span>
  <span data-ttu-id="aadae-103">Retorna o maior inteiro que é menor que ou igual a uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="aadae-103">Returns the largest integer that is less than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aadae-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aadae-104">Syntax</span></span>  
  
```  
  
FLOOR(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="aadae-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="aadae-105">Arguments</span></span>  
 <span data-ttu-id="aadae-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="aadae-106">*numeric_expression*</span></span>  
 <span data-ttu-id="aadae-107">É uma expressão numérica válida.</span><span class="sxs-lookup"><span data-stu-id="aadae-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="aadae-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="aadae-108">Result Types</span></span>  
 <span data-ttu-id="aadae-109">O tipo de dados numérico da expressão do argumento.</span><span class="sxs-lookup"><span data-stu-id="aadae-109">The numeric data type of the argument expression.</span></span> <span data-ttu-id="aadae-110">O resultado é a parte inteira do valor calculado no mesmo tipo de dados que *numeric_expression.*</span><span class="sxs-lookup"><span data-stu-id="aadae-110">The result is the integer portion of the calculated value in the same data type as *numeric_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aadae-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="aadae-111">Remarks</span></span>  
 <span data-ttu-id="aadae-112">FLOOR retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="aadae-112">FLOOR returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="aadae-113">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="aadae-113">Expression Examples</span></span>  
 <span data-ttu-id="aadae-114">Estes exemplos aplicam a função FLOOR aos valores positivos, negativos e zerados.</span><span class="sxs-lookup"><span data-stu-id="aadae-114">These examples apply the FLOOR function to positive, negative, and zero values.</span></span>  
  
```  
FLOOR(123.45)  
```  
  
 <span data-ttu-id="aadae-115">Retorna 123.00</span><span class="sxs-lookup"><span data-stu-id="aadae-115">Returns 123.00</span></span>  
  
```  
FLOOR(-123.45)  
```  
  
 <span data-ttu-id="aadae-116">Retorna -124.00</span><span class="sxs-lookup"><span data-stu-id="aadae-116">Returns -124.00</span></span>  
  
```  
FLOOR(0.00)  
```  
  
 <span data-ttu-id="aadae-117">Retorna 0.00</span><span class="sxs-lookup"><span data-stu-id="aadae-117">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aadae-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aadae-118">See Also</span></span>  
 <span data-ttu-id="aadae-119">[CEILING &#40;Expressão do SSIS&#41;](ceiling-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="aadae-119">[CEILING &#40;SSIS Expression&#41;](ceiling-ssis-expression.md) </span></span>  
 [<span data-ttu-id="aadae-120">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="aadae-120">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
