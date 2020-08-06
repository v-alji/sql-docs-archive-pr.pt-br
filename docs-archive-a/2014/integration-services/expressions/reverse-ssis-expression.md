---
title: REVERSE (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REVERSE function
- reverse character expressions
ms.assetid: bcebcc55-7247-4896-8f53-4d582d58cfb4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2ace136eed0abcb9df7b25d9370c46d7556c1d48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681023"
---
# <a name="reverse-ssis-expression"></a><span data-ttu-id="415e0-102">REVERSE (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="415e0-102">REVERSE (SSIS Expression)</span></span>
  <span data-ttu-id="415e0-103">Retorna uma expressão character na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="415e0-103">Returns a character expression in reverse order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="415e0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="415e0-104">Syntax</span></span>  
  
```  
  
REVERSE(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="415e0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="415e0-105">Arguments</span></span>  
 <span data-ttu-id="415e0-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="415e0-106">*character_expression*</span></span>  
 <span data-ttu-id="415e0-107">É uma expressão de caractere a ser invertida.</span><span class="sxs-lookup"><span data-stu-id="415e0-107">Is a character expression to be reversed.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="415e0-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="415e0-108">Result Types</span></span>  
 <span data-ttu-id="415e0-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="415e0-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="415e0-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="415e0-110">Remarks</span></span>  
 <span data-ttu-id="415e0-111">O argumento *character_expression* deve ter o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="415e0-111">The *character_expression* argument must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="415e0-112">REVERSE retornará um resultado nulo se *character_expression* for nulo.</span><span class="sxs-lookup"><span data-stu-id="415e0-112">REVERSE returns a null result if *character_expression* is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="415e0-113">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="415e0-113">Expression Examples</span></span>  
 <span data-ttu-id="415e0-114">Este exemplo usa um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="415e0-114">This example uses a string literal.</span></span> <span data-ttu-id="415e0-115">O resultado de retorno é "ekiB niatnuoM".</span><span class="sxs-lookup"><span data-stu-id="415e0-115">The return result is "ekiB niatnuoM".</span></span>  
  
```  
REVERSE("Mountain Bike")  
```  
  
 <span data-ttu-id="415e0-116">Este exemplo usa uma variável.</span><span class="sxs-lookup"><span data-stu-id="415e0-116">This example uses a variable.</span></span> <span data-ttu-id="415e0-117">Se **Name** contiver Touring Bike, o resultado de retorno será "ekiB gniruoT".</span><span class="sxs-lookup"><span data-stu-id="415e0-117">If **Name** contains Touring Bike, the return result is "ekiB gniruoT".</span></span>  
  
```  
REVERSE(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="415e0-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="415e0-118">See Also</span></span>  
 [<span data-ttu-id="415e0-119">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="415e0-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
