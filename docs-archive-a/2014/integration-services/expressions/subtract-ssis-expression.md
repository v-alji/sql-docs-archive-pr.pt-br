---
title: '- (Subtrair) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (subtract)'
- subtract operator (-)
ms.assetid: b48da086-37dd-460a-8a4b-912f52c9b158
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 79c47689baf47c33952c6b208ac622e9920d05fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681003"
---
# <a name="--subtract-ssis-expression"></a><span data-ttu-id="9294a-102">- (Subtração) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="9294a-102">- (Subtract) (SSIS Expression)</span></span>
  <span data-ttu-id="9294a-103">Subtrai a segunda expressão numérica da primeira.</span><span class="sxs-lookup"><span data-stu-id="9294a-103">Subtracts the second numeric expression from the first one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9294a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9294a-104">Syntax</span></span>  
  
```  
  
numeric_expression1 - numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9294a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9294a-105">Arguments</span></span>  
 <span data-ttu-id="9294a-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="9294a-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="9294a-107">É qualquer expressão válida de um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="9294a-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="9294a-108">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="9294a-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9294a-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="9294a-109">Result Types</span></span>  
 <span data-ttu-id="9294a-110">Determinado pelos tipos de dados dos dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="9294a-110">Determined by the data types of the two arguments.</span></span> <span data-ttu-id="9294a-111">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9294a-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9294a-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="9294a-112">Remarks</span></span>  
 <span data-ttu-id="9294a-113">Coloque a expressão unária minus em parênteses para assegurar que ela seja avaliada na ordem correta</span><span class="sxs-lookup"><span data-stu-id="9294a-113">Enclose the minus unary expression in parenthesis to ensure that the expression is evaluated in the correct order</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9294a-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="9294a-114">Remarks</span></span>  
 <span data-ttu-id="9294a-115">Se qualquer operando for nulo, o resultado será nulo.</span><span class="sxs-lookup"><span data-stu-id="9294a-115">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="9294a-116">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="9294a-116">Expression Examples</span></span>  
 <span data-ttu-id="9294a-117">Este exemplo subtrai literais numéricas.</span><span class="sxs-lookup"><span data-stu-id="9294a-117">This example subtracts numeric literals.</span></span>  
  
```  
5 - 6.09  
```  
  
 <span data-ttu-id="9294a-118">Este exemplo subtrai o valor na coluna **StandardCost** do valor na coluna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="9294a-118">This example subtracts the value in the **StandardCost** column from the value in the **ListPrice** column.</span></span>  
  
```  
ListPrice - StandardCost  
```  
  
 <span data-ttu-id="9294a-119">Este exemplo subtrai um valor calculado da coluna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="9294a-119">This example subtracts a calculated value from the **ListPrice** column.</span></span> <span data-ttu-id="9294a-120">A variável **Discount%** deve estar entre colchetes porque o nome inclui o caractere % .</span><span class="sxs-lookup"><span data-stu-id="9294a-120">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="9294a-121">Para obter mais informações, consulte [Identificadores &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="9294a-121">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="9294a-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9294a-122">See Also</span></span>  
 <span data-ttu-id="9294a-123">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="9294a-123">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="9294a-124">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="9294a-124">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
