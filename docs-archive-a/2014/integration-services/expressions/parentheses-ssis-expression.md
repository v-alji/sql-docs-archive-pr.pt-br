---
title: () (Parênteses) (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- () (parentheses operator)
- evaluation order [Integration Services]
- parentheses operator ()
ms.assetid: 931e10eb-1707-4121-b2f1-43565561119f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e390e10e485bd9cc22480300b6a9c33098bda8f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684806"
---
# <a name="-parentheses-ssis-expression"></a><span data-ttu-id="8de68-102">() (Parênteses) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="8de68-102">() (Parentheses) (SSIS Expression)</span></span>
  <span data-ttu-id="8de68-103">Identifica a ordem de avaliação de expressões.</span><span class="sxs-lookup"><span data-stu-id="8de68-103">Identifies the evaluation order of expressions.</span></span> <span data-ttu-id="8de68-104">Expressões incluídas em parênteses têm a precedência de avaliação mais alta.</span><span class="sxs-lookup"><span data-stu-id="8de68-104">Expressions enclosed in parentheses have the highest evaluation precedence.</span></span> <span data-ttu-id="8de68-105">São avaliadas expressões aninhadas incluídas em parênteses na ordem interno-para-externo.</span><span class="sxs-lookup"><span data-stu-id="8de68-105">Nested expressions enclosed in parentheses are evaluated in inner-to-outer order.</span></span>  
  
 <span data-ttu-id="8de68-106">Parênteses também são usados para facilitar a compreensão de expressões complexas.</span><span class="sxs-lookup"><span data-stu-id="8de68-106">Parentheses are also used to make complex expressions easier to understand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de68-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8de68-107">Syntax</span></span>  
  
```  
  
(expression)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="8de68-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8de68-108">Arguments</span></span>  
 <span data-ttu-id="8de68-109">*expressão*</span><span class="sxs-lookup"><span data-stu-id="8de68-109">*expression*</span></span>  
 <span data-ttu-id="8de68-110">É qualquer expressão válida.</span><span class="sxs-lookup"><span data-stu-id="8de68-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8de68-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="8de68-111">Result Types</span></span>  
 <span data-ttu-id="8de68-112">O tipo de dados de *expression*.</span><span class="sxs-lookup"><span data-stu-id="8de68-112">The data type of *expression*.</span></span> <span data-ttu-id="8de68-113">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="8de68-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="8de68-114">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="8de68-114">Expression Examples</span></span>  
 <span data-ttu-id="8de68-115">Este exemplo mostra como o uso de parênteses modifica a precedência de operadores.</span><span class="sxs-lookup"><span data-stu-id="8de68-115">This example shows how the use of parenthesis modifies the precedence of operators.</span></span> <span data-ttu-id="8de68-116">A primeira expressão é avaliada como 100, embora a segunda seja avaliada como 31.</span><span class="sxs-lookup"><span data-stu-id="8de68-116">The first expression evaluates to 100, whereas the second one evaluates to 31.</span></span>  
  
```  
(5 + 5) * (4 + 6)  
5 + 5 * 4 + 6  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="8de68-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8de68-117">See Also</span></span>  
 <span data-ttu-id="8de68-118">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="8de68-118">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="8de68-119">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8de68-119">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
