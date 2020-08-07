---
title: LOG (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- base-10 logarithms
- LOG function
ms.assetid: f7fccace-c178-4e13-bde9-7dc4ef1d98fa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0de84c1a92f94507bcc69c47cc4d9b6cda50a4f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575963"
---
# <a name="log-ssis-expression"></a><span data-ttu-id="04bf6-102">LOG (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="04bf6-102">LOG (SSIS Expression)</span></span>
  <span data-ttu-id="04bf6-103">Retorna o logaritmo de base 10 de uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="04bf6-103">Returns the base-10 logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04bf6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="04bf6-104">Syntax</span></span>  
  
```  
  
LOG(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="04bf6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="04bf6-105">Arguments</span></span>  
 <span data-ttu-id="04bf6-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="04bf6-106">*numeric_expression*</span></span>  
 <span data-ttu-id="04bf6-107">É uma expressão numérica válida não zero ou não negativa.</span><span class="sxs-lookup"><span data-stu-id="04bf6-107">Is a valid nonzero or nonnegative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="04bf6-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="04bf6-108">Result Types</span></span>  
 <span data-ttu-id="04bf6-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="04bf6-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04bf6-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="04bf6-110">Remarks</span></span>  
 <span data-ttu-id="04bf6-111">A *expressão numérica* é convertida para o tipo de dados DT_R8 antes de o logaritmo ser computado.</span><span class="sxs-lookup"><span data-stu-id="04bf6-111">The *numeric expression* is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="04bf6-112">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="04bf6-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="04bf6-113">Se *numeric_expression* for avaliado como zero ou um valor negativo, o resultado de retorno será nulo.</span><span class="sxs-lookup"><span data-stu-id="04bf6-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="04bf6-114">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="04bf6-114">Expression Examples</span></span>  
 <span data-ttu-id="04bf6-115">Esse exemplo usa um literal numérico.</span><span class="sxs-lookup"><span data-stu-id="04bf6-115">This example uses a numeric literal.</span></span> <span data-ttu-id="04bf6-116">A função retorna o valor 1.988291341907488.</span><span class="sxs-lookup"><span data-stu-id="04bf6-116">The function returns the value 1.988291341907488.</span></span>  
  
```  
LOG(97.34)  
```  
  
 <span data-ttu-id="04bf6-117">Esse exemplo usa a coluna **Length**.</span><span class="sxs-lookup"><span data-stu-id="04bf6-117">This example uses the column **Length**.</span></span> <span data-ttu-id="04bf6-118">Se o valor da coluna for 101.24, a função retornará 2.005352136486217.</span><span class="sxs-lookup"><span data-stu-id="04bf6-118">If the column is 101.24, the function returns 2.005352136486217.</span></span>  
  
```  
LOG(Length)   
```  
  
 <span data-ttu-id="04bf6-119">Esse exemplo usa a variável **Length**.</span><span class="sxs-lookup"><span data-stu-id="04bf6-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="04bf6-120">A variável deve ter um tipo de dados numérico ou a expressão deve incluir uma conversão explícita para um tipo de dados [!INCLUDE[ssIS](../../includes/ssis-md.md)] numérico.</span><span class="sxs-lookup"><span data-stu-id="04bf6-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span> <span data-ttu-id="04bf6-121">Se **Length** for 234.567, a função retornará 2.370266913465859.</span><span class="sxs-lookup"><span data-stu-id="04bf6-121">If **Length** is 234.567, the function returns 2.370266913465859.</span></span>  
  
```  
LOG(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="04bf6-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="04bf6-122">See Also</span></span>  
 <span data-ttu-id="04bf6-123">[EXP &#40;Expressão SSIS&#41;](exp-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="04bf6-123">[EXP &#40;SSIS Expression&#41;](exp-ssis-expression.md) </span></span>  
 <span data-ttu-id="04bf6-124">[LN &#40;Expressão SSIS&#41;](ln-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="04bf6-124">[LN &#40;SSIS Expression&#41;](ln-ssis-expression.md) </span></span>  
 [<span data-ttu-id="04bf6-125">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="04bf6-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
