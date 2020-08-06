---
title: SIGN (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- positive values [Integration Services]
- SIGN function
- negative values
ms.assetid: 1547db08-4329-4781-91c2-36898ed71b15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a34992b0029cd378274e38ce4e37fcd313d2b788
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681016"
---
# <a name="sign-ssis-expression"></a><span data-ttu-id="3ce69-102">SIGN (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="3ce69-102">SIGN (SSIS Expression)</span></span>
  <span data-ttu-id="3ce69-103">Retorna o sinal positivo (+1), negativo (-1) ou zero (0) de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="3ce69-103">Returns the positive (+1), negative (-1), or zero (0) sign of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce69-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3ce69-104">Syntax</span></span>  
  
```  
  
SIGN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="3ce69-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3ce69-105">Arguments</span></span>  
 <span data-ttu-id="3ce69-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="3ce69-106">*numeric_expression*</span></span>  
 <span data-ttu-id="3ce69-107">É uma expressão numérica assinada válida.</span><span class="sxs-lookup"><span data-stu-id="3ce69-107">Is a valid signed numeric expression.</span></span> <span data-ttu-id="3ce69-108">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3ce69-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3ce69-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="3ce69-109">Result Types</span></span>  
 <span data-ttu-id="3ce69-110">DT_I4</span><span class="sxs-lookup"><span data-stu-id="3ce69-110">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ce69-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="3ce69-111">Remarks</span></span>  
 <span data-ttu-id="3ce69-112">SIGN retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="3ce69-112">SIGN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3ce69-113">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="3ce69-113">Expression Examples</span></span>  
 <span data-ttu-id="3ce69-114">Este exemplo retorna o sinal de um literal numérico.</span><span class="sxs-lookup"><span data-stu-id="3ce69-114">This example returns the sign of a numeric literal.</span></span> <span data-ttu-id="3ce69-115">O resultado de retorno é -1.</span><span class="sxs-lookup"><span data-stu-id="3ce69-115">The return result is -1.</span></span>  
  
```  
SIGN(-123.45)  
```  
  
 <span data-ttu-id="3ce69-116">Este exemplo retorna o sinal do resultado da subtração da coluna **StandardCost** da coluna **DealerPrice** .</span><span class="sxs-lookup"><span data-stu-id="3ce69-116">This example returns the sign of the result of subtracting the **StandardCost** column from the **DealerPrice** column.</span></span>  
  
```  
SIGN(DealerPrice - StandardCost)  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ce69-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ce69-117">See Also</span></span>  
 [<span data-ttu-id="3ce69-118">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3ce69-118">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
