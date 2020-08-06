---
title: '- (Negar) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (negative)'
- negative operator (-)
ms.assetid: f0118dfc-aced-4de2-953e-5ebf9c962b8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2a2d8ba292f2d24633598ab080ddf75ded5e8bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683126"
---
# <a name="--negate-ssis-expression"></a><span data-ttu-id="1128d-102">- (Negação) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="1128d-102">- (Negate) (SSIS Expression)</span></span>
  <span data-ttu-id="1128d-103">Nega uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="1128d-103">Negates a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1128d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1128d-104">Syntax</span></span>  
  
```  
  
-numeric_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1128d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1128d-105">Arguments</span></span>  
 <span data-ttu-id="1128d-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="1128d-106">*numeric_expression*</span></span>  
 <span data-ttu-id="1128d-107">É qualquer expressão válida de um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="1128d-107">Is any valid expression of any numeric data type.</span></span> <span data-ttu-id="1128d-108">Há suporte somente para tipos de dados numéricos assinados.</span><span class="sxs-lookup"><span data-stu-id="1128d-108">Only signed numeric data types are supported.</span></span> <span data-ttu-id="1128d-109">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1128d-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1128d-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="1128d-110">Result Types</span></span>  
 <span data-ttu-id="1128d-111">Retorna o tipo de dados de *numeric_expression*.</span><span class="sxs-lookup"><span data-stu-id="1128d-111">Returns the data type of *numeric_expression*.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="1128d-112">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="1128d-112">Expression Examples</span></span>  
 <span data-ttu-id="1128d-113">Esse exemplo nega o valor da variável **Counter** e adiciona o literal numérico 50.</span><span class="sxs-lookup"><span data-stu-id="1128d-113">This example negates the value of the **Counter** variable and adds the numeric literal 50.</span></span>  
  
```  
-@Counter + 50  
```  
  
## <a name="see-also"></a><span data-ttu-id="1128d-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1128d-114">See Also</span></span>  
 <span data-ttu-id="1128d-115">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="1128d-115">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="1128d-116">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1128d-116">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
