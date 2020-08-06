---
title: ROUND (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- rounding expressions
- ROUND function [SSIS]
ms.assetid: 376f1947-4fc5-4611-ad86-823e4db1b468
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d77045787eafbc3dd402db9982d8d7a98190bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681019"
---
# <a name="round-ssis-expression"></a><span data-ttu-id="dfacb-102">ROUND (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="dfacb-102">ROUND (SSIS Expression)</span></span>
  <span data-ttu-id="dfacb-103">Retorna uma expressão numérica arredondada ao comprimento ou precisão especificados.</span><span class="sxs-lookup"><span data-stu-id="dfacb-103">Returns a numeric expression that is rounded to the specified length or precision.</span></span> <span data-ttu-id="dfacb-104">O parâmetro de comprimento deve ser avaliado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="dfacb-104">The length parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfacb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dfacb-105">Syntax</span></span>  
  
```  
  
ROUND(numeric_expression,length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="dfacb-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dfacb-106">Arguments</span></span>  
 <span data-ttu-id="dfacb-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="dfacb-107">*numeric_expression*</span></span>  
 <span data-ttu-id="dfacb-108">É uma expressão de um tipo de numérico válido.</span><span class="sxs-lookup"><span data-stu-id="dfacb-108">Is an expression of a valid numeric type.</span></span> <span data-ttu-id="dfacb-109">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="dfacb-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="dfacb-110">*length*</span><span class="sxs-lookup"><span data-stu-id="dfacb-110">*length*</span></span>  
 <span data-ttu-id="dfacb-111">É uma expressão de inteiro.</span><span class="sxs-lookup"><span data-stu-id="dfacb-111">Is an integer expression.</span></span> <span data-ttu-id="dfacb-112">Precisão para a qual *numeric_expression* é arredondada.</span><span class="sxs-lookup"><span data-stu-id="dfacb-112">It is the precision to which *numeric_expression* is rounded.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="dfacb-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="dfacb-113">Result Types</span></span>  
 <span data-ttu-id="dfacb-114">O mesmo tipo que *numeric*_*expression.*</span><span class="sxs-lookup"><span data-stu-id="dfacb-114">The same type as *numeric*_*expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfacb-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="dfacb-115">Remarks</span></span>  
 <span data-ttu-id="dfacb-116">O argumento *length* deve ser avaliado como um inteiro positivo ou zero.</span><span class="sxs-lookup"><span data-stu-id="dfacb-116">The *length* argument must evaluate to a positive integer or zero.</span></span>  
  
 <span data-ttu-id="dfacb-117">ROUND retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="dfacb-117">ROUND returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="dfacb-118">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="dfacb-118">Expression Examples</span></span>  
 <span data-ttu-id="dfacb-119">Estes exemplos arredondam literais numéricos para um comprimento de três.</span><span class="sxs-lookup"><span data-stu-id="dfacb-119">These examples round numeric literals to a length of three.</span></span> <span data-ttu-id="dfacb-120">O primeiro resultado de retorno é 137.1570, o segundo em 137.1580.</span><span class="sxs-lookup"><span data-stu-id="dfacb-120">The first return result is 137.1570, the second 137.1580.</span></span>  
  
```  
ROUND(137.1574,3)  
ROUND(137.1575,3)  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfacb-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dfacb-121">See Also</span></span>  
 [<span data-ttu-id="dfacb-122">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="dfacb-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
