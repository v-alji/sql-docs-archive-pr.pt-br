---
title: ABS (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ABS function
- absolute positive value
ms.assetid: 156747f6-e016-44cf-9a9f-ae8e4a1b4f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f429dda94282646ef769a1c393f9fa54b56e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575982"
---
# <a name="abs-ssis-expression"></a><span data-ttu-id="52b61-102">ABS (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="52b61-102">ABS (SSIS Expression)</span></span>
  <span data-ttu-id="52b61-103">Retorna o valor positivo absoluto de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="52b61-103">Returns the absolute, positive value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52b61-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="52b61-104">Syntax</span></span>  
  
```  
  
ABS(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="52b61-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="52b61-105">Arguments</span></span>  
 <span data-ttu-id="52b61-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="52b61-106">*numeric_expression*</span></span>  
 <span data-ttu-id="52b61-107">É uma expressão numérica assinada ou não assinada.</span><span class="sxs-lookup"><span data-stu-id="52b61-107">Is a signed or unsigned numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="52b61-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="52b61-108">Result Types</span></span>  
 <span data-ttu-id="52b61-109">O tipo de dados da expressão numérica submetido à função.</span><span class="sxs-lookup"><span data-stu-id="52b61-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52b61-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="52b61-110">Remarks</span></span>  
 <span data-ttu-id="52b61-111">ABS retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="52b61-111">ABS returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="52b61-112">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="52b61-112">Expression Examples</span></span>  
 <span data-ttu-id="52b61-113">Estes exemplos se aplicam à função ABS para um número positivo e um negativo.</span><span class="sxs-lookup"><span data-stu-id="52b61-113">These examples apply the ABS function to a positive and a negative number.</span></span> <span data-ttu-id="52b61-114">Ambos retornam 1.23.</span><span class="sxs-lookup"><span data-stu-id="52b61-114">Both return 1.23.</span></span>  
  
```  
ABS(-1.23)  
ABS(1.23)  
```  
  
 <span data-ttu-id="52b61-115">Este exemplo se aplica à função ABS para uma expressão que subtrai valores nas variáveis **HighTemperature** e **LowTempature**.</span><span class="sxs-lookup"><span data-stu-id="52b61-115">This example applies the ABS function to an expression that subtracts values in the variables **HighTemperature** and **LowTempature**.</span></span>  
  
```  
ABS(@HighTemperature - @LowTemperature)  
```  
  
## <a name="see-also"></a><span data-ttu-id="52b61-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="52b61-116">See Also</span></span>  
 [<span data-ttu-id="52b61-117">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="52b61-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
