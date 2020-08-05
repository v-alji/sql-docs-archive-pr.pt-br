---
title: '* (Multiplicar) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '* (multiply operator)'
- multiply operator (*)
ms.assetid: d457f052-ffbb-4485-833f-f4bed4349b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16d8429a869b60be31a94244a2ce47d515770c6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573200"
---
# <a name="-multiply-ssis-expression"></a><span data-ttu-id="71acc-102">\* (Multiplicar) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="71acc-102">\* (Multiply) (SSIS Expression)</span></span>
  <span data-ttu-id="71acc-103">Multiplica duas expressões numéricas.</span><span class="sxs-lookup"><span data-stu-id="71acc-103">Multiplies two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71acc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="71acc-104">Syntax</span></span>  
  
```  
  
numeric_expression1 * numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="71acc-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="71acc-105">Arguments</span></span>  
 <span data-ttu-id="71acc-106">*numeric_expression1, numeric_expression2*</span><span class="sxs-lookup"><span data-stu-id="71acc-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="71acc-107">É qualquer expressão válida de um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="71acc-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="71acc-108">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="71acc-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="71acc-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="71acc-109">Result Types</span></span>  
 <span data-ttu-id="71acc-110">Determinado por tipos de dados dos dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="71acc-110">Determined by data types of the two arguments.</span></span> <span data-ttu-id="71acc-111">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="71acc-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71acc-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="71acc-112">Remarks</span></span>  
 <span data-ttu-id="71acc-113">Se qualquer operando for nulo, o resultado será nulo.</span><span class="sxs-lookup"><span data-stu-id="71acc-113">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="71acc-114">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="71acc-114">Expression Examples</span></span>  
 <span data-ttu-id="71acc-115">Este exemplo multiplica literais numéricos.</span><span class="sxs-lookup"><span data-stu-id="71acc-115">This example multiplies numeric literals.</span></span>  
  
```  
5 * 6.09  
```  
  
 <span data-ttu-id="71acc-116">Este exemplo multiplica valores na coluna **ListPrice** por 10%.</span><span class="sxs-lookup"><span data-stu-id="71acc-116">This example multiplies values in the **ListPrice** column by 10 percent.</span></span>  
  
```  
ListPrice * .10  
```  
  
 <span data-ttu-id="71acc-117">Este exemplo subtrai o resultado de uma expressão da coluna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="71acc-117">This example subtracts the result of an expression from the **ListPrice** column.</span></span> <span data-ttu-id="71acc-118">A variável **Discount%** deve estar entre colchetes porque o nome inclui o caractere % .</span><span class="sxs-lookup"><span data-stu-id="71acc-118">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="71acc-119">Para obter mais informações, consulte [Identificadores &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="71acc-119">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="71acc-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71acc-120">See Also</span></span>  
 <span data-ttu-id="71acc-121">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="71acc-121">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="71acc-122">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="71acc-122">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
