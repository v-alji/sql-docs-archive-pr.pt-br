---
title: CEILING (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- smallest integer great than or equal to expression
- CEILING function [SSIS]
ms.assetid: c35bd4ee-1ab6-46ab-89a7-cf771527faa2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd2f9f455226925d6bf00842e80a8713e6c72771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583735"
---
# <a name="ceiling-ssis-expression"></a><span data-ttu-id="ea0af-102">CEILING (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="ea0af-102">CEILING (SSIS Expression)</span></span>
  <span data-ttu-id="ea0af-103">Retorna o menor inteiro que é maior que ou igual a uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="ea0af-103">Returns the smallest integer that is greater than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea0af-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ea0af-104">Syntax</span></span>  
  
```  
  
CEILING(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ea0af-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ea0af-105">Arguments</span></span>  
 <span data-ttu-id="ea0af-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="ea0af-106">*numeric_expression*</span></span>  
 <span data-ttu-id="ea0af-107">É uma expressão numérica válida.</span><span class="sxs-lookup"><span data-stu-id="ea0af-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ea0af-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="ea0af-108">Result Types</span></span>  
 <span data-ttu-id="ea0af-109">O tipo de dados da expressão numérica submetido à função.</span><span class="sxs-lookup"><span data-stu-id="ea0af-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea0af-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="ea0af-110">Remarks</span></span>  
 <span data-ttu-id="ea0af-111">CEILING retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="ea0af-111">CEILING returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ea0af-112">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="ea0af-112">Expression Examples</span></span>  
 <span data-ttu-id="ea0af-113">Estes exemplos se aplicam à função CEILING para valores positivo, negativo e zero.</span><span class="sxs-lookup"><span data-stu-id="ea0af-113">These examples apply the CEILING function to positive, negative, and zero values.</span></span>  
  
```  
CEILING(123.74)  
```  
  
 <span data-ttu-id="ea0af-114">Retorna 124,00</span><span class="sxs-lookup"><span data-stu-id="ea0af-114">Returns 124.00</span></span>  
  
```  
CEILING(-124.27)  
```  
  
 <span data-ttu-id="ea0af-115">Retorna -124.00</span><span class="sxs-lookup"><span data-stu-id="ea0af-115">Returns -124.00</span></span>  
  
```  
CEILING(0.00)  
```  
  
 <span data-ttu-id="ea0af-116">Retorna 0.00</span><span class="sxs-lookup"><span data-stu-id="ea0af-116">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea0af-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea0af-117">See Also</span></span>  
 <span data-ttu-id="ea0af-118">[FLOOR &#40;Expressão SSIS&#41;](floor-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ea0af-118">[FLOOR &#40;SSIS Expression&#41;](floor-ssis-expression.md) </span></span>  
 [<span data-ttu-id="ea0af-119">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ea0af-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
