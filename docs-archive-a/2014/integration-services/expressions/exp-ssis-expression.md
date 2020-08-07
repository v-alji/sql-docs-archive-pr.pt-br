---
title: EXP (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- exponential functions
- EXP function
ms.assetid: 4cd96d3c-58c9-4a67-a6f6-b72758232912
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 150c92355ab3e0d3a028c98defe2e2fa9a1bf8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574787"
---
# <a name="exp-ssis-expression"></a><span data-ttu-id="98059-102">EXP (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="98059-102">EXP (SSIS Expression)</span></span>
  <span data-ttu-id="98059-103">Retorna o expoente para a base e de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="98059-103">Returns the exponent to base e of a numeric expression.</span></span> <span data-ttu-id="98059-104">A função EXP complementa a ação da função LN e, às vezes, é chamado de antilogaritmo.</span><span class="sxs-lookup"><span data-stu-id="98059-104">The EXP function complements the action of the LN function and is sometimes referred to as the antilogarithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98059-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="98059-105">Syntax</span></span>  
  
```  
  
EXP(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="98059-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="98059-106">Arguments</span></span>  
 <span data-ttu-id="98059-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="98059-107">*numeric_expression*</span></span>  
 <span data-ttu-id="98059-108">É uma expressão numérica válida.</span><span class="sxs-lookup"><span data-stu-id="98059-108">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="98059-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="98059-109">Result Types</span></span>  
 <span data-ttu-id="98059-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="98059-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98059-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="98059-111">Remarks</span></span>  
 <span data-ttu-id="98059-112">A expressão numérica é lançada para o tipo de dados de DT_R8 antes de o expoente ser computado.</span><span class="sxs-lookup"><span data-stu-id="98059-112">The numeric expression is cast to the DT_R8 data type before the exponent is computed.</span></span> <span data-ttu-id="98059-113">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="98059-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="98059-114">O resultado de retorno sempre é um número positivo.</span><span class="sxs-lookup"><span data-stu-id="98059-114">The return result is always a positive number.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="98059-115">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="98059-115">Expression Examples</span></span>  
 <span data-ttu-id="98059-116">Estes exemplos se aplicam à função EXP para valores positivo e negativos e para zero.</span><span class="sxs-lookup"><span data-stu-id="98059-116">These examples apply the EXP function to positive and negative values and to zero.</span></span>  
  
```  
EXP(74)  
```  
  
 <span data-ttu-id="98059-117">Retorna 1.373382979540176E+32.</span><span class="sxs-lookup"><span data-stu-id="98059-117">Returns 1.373382979540176E+32.</span></span>  
  
```  
EXP(-27)  
```  
  
 <span data-ttu-id="98059-118">Retorna 1.879528816539083E-12.</span><span class="sxs-lookup"><span data-stu-id="98059-118">Returns 1.879528816539083E-12.</span></span>  
  
```  
EXP(0)  
```  
  
 <span data-ttu-id="98059-119">Retorna 1.</span><span class="sxs-lookup"><span data-stu-id="98059-119">Returns 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98059-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98059-120">See Also</span></span>  
 <span data-ttu-id="98059-121">[LOG &#40;Expressão SSIS&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="98059-121">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="98059-122">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="98059-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
