---
title: + (Adicionar) (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- + (add)
- add operator (+)
- adding expressions
ms.assetid: 44df4154-fed5-4e7f-9995-e703a0164f6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fe1e8f2118e6328582cb24abfd44eef5f3b15f79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575980"
---
# <a name="-add-ssis"></a><span data-ttu-id="c61c3-102">+ (Adição) (SSIS)</span><span class="sxs-lookup"><span data-stu-id="c61c3-102">+ (Add) (SSIS)</span></span>
  <span data-ttu-id="c61c3-103">Soma duas expressões numéricas.</span><span class="sxs-lookup"><span data-stu-id="c61c3-103">Adds two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61c3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c61c3-104">Syntax</span></span>  
  
```  
  
numeric_expression1 + numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c61c3-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c61c3-105">Arguments</span></span>  
 <span data-ttu-id="c61c3-106">*numeric_expression1, numeric_ expression2*</span><span class="sxs-lookup"><span data-stu-id="c61c3-106">*numeric_expression1, numeric_ expression2*</span></span>  
 <span data-ttu-id="c61c3-107">É qualquer expressão válida de um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="c61c3-107">Is any valid expression of a numeric data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c61c3-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c61c3-108">Result Types</span></span>  
 <span data-ttu-id="c61c3-109">Determinado por tipos de dados dos dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="c61c3-109">Determined by data types of the two arguments.</span></span> <span data-ttu-id="c61c3-110">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c61c3-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c61c3-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="c61c3-111">Remarks</span></span>  
 <span data-ttu-id="c61c3-112">Se qualquer operando for nulo, o resultado será nulo.</span><span class="sxs-lookup"><span data-stu-id="c61c3-112">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c61c3-113">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="c61c3-113">Expression Examples</span></span>  
 <span data-ttu-id="c61c3-114">Este exemplo soma literais numéricos.</span><span class="sxs-lookup"><span data-stu-id="c61c3-114">This example adds numeric literals.</span></span>  
  
```  
5 + 6.09 + 7.0  
```  
  
 <span data-ttu-id="c61c3-115">Este exemplo soma valores nas colunas **VacationHours** e **SickLeaveHours** .</span><span class="sxs-lookup"><span data-stu-id="c61c3-115">This example adds values in the **VacationHours** and **SickLeaveHours** columns.</span></span>  
  
```  
VacationHours + SickLeaveHours  
```  
  
 <span data-ttu-id="c61c3-116">Este exemplo acrescenta um valor calculado à coluna **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="c61c3-116">This example adds a calculated value to the **StandardCost** column.</span></span> <span data-ttu-id="c61c3-117">A variável **Profit%** deve estar entre colchetes porque o nome inclui o caractere % .</span><span class="sxs-lookup"><span data-stu-id="c61c3-117">The variable **Profit%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="c61c3-118">Para obter mais informações, consulte [Identificadores &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="c61c3-118">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
StandardCost + (StandardCost * @[Profit%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="c61c3-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c61c3-119">See Also</span></span>  
 <span data-ttu-id="c61c3-120">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="c61c3-120">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="c61c3-121">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c61c3-121">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
