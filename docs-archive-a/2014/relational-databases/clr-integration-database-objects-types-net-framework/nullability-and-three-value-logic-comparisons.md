---
title: Comparações de lógica de três valores e nulidade | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- precision [CLR integration]
- overflow detections [CLR integration]
- null values [CLR integration]
- three-value logic comparisons [CLR integration]
- data types [CLR integration]
- SqlBoolean data type
ms.assetid: 13da4c7f-1010-4b2d-a63c-c69b6bfd96f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b8000c1c28d5a1d3d129b6e8d01c4ab2fbbbc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685782"
---
# <a name="nullability-and-three-value-logic-comparisons"></a><span data-ttu-id="12fb5-102">Comparações de lógica de três valores e nulidade</span><span class="sxs-lookup"><span data-stu-id="12fb5-102">Nullability and Three-Value Logic Comparisons</span></span>
  <span data-ttu-id="12fb5-103">Se estiver familiarizado com os tipos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você achará a semântica e a precisão semelhantes no `System.Data.SqlTypes` namespace de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12fb5-103">If you are familiar with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, you will find similar semantics and precision in the `System.Data.SqlTypes` namespace in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="12fb5-104">No entanto, há algumas diferenças, e este tópico aborda a mais importante delas.</span><span class="sxs-lookup"><span data-stu-id="12fb5-104">There are some differences, however, and this topic covers the most important of these differences.</span></span>  
  
## <a name="null-values"></a><span data-ttu-id="12fb5-105">Valores NULL</span><span class="sxs-lookup"><span data-stu-id="12fb5-105">NULL Values</span></span>  
 <span data-ttu-id="12fb5-106">A principal diferença entre os tipos de dados CLR (Common Language Runtime) nativos e os tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é que os primeiros não permitem valores NULL, ao passo que os últimos fornecem uma semântica NULL completa.</span><span class="sxs-lookup"><span data-stu-id="12fb5-106">A primary difference between native common language runtime (CLR) data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types is that the former do not allow for NULL values, while the latter provide full NULL semantics.</span></span>  
  
 <span data-ttu-id="12fb5-107">As comparações são afetadas por valores NULL.</span><span class="sxs-lookup"><span data-stu-id="12fb5-107">Comparisons are affected by NULL values.</span></span> <span data-ttu-id="12fb5-108">Durante a comparação entre dois valores x e y, caso x ou y seja NULL, algumas comparações lógicas são avaliadas como UNKNOWN, e não como true ou false.</span><span class="sxs-lookup"><span data-stu-id="12fb5-108">When comparing two values x and y, if either x or y is NULL, then some logical comparisons evaluate to an UNKNOWN value rather than true or false.</span></span>  
  
## <a name="sqlboolean-data-type"></a><span data-ttu-id="12fb5-109">Tipo de dados SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="12fb5-109">SqlBoolean Data Type</span></span>  
 <span data-ttu-id="12fb5-110">O namespace `System.Data.SqlTypes` introduz um tipo `SqlBoolean` para representar essa lógica de 3 valores.</span><span class="sxs-lookup"><span data-stu-id="12fb5-110">The `System.Data.SqlTypes` namespace introduces a `SqlBoolean` type to represent this 3-value logic.</span></span> <span data-ttu-id="12fb5-111">Comparações entre qualquer `SqlTypes` retornam um tipo de valor `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="12fb5-111">Comparisons between any `SqlTypes` return a `SqlBoolean` value type.</span></span> <span data-ttu-id="12fb5-112">O valor UNKNOWN é representado pelo valor nulo do tipo `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="12fb5-112">The UNKNOWN value is represented by the null value of the `SqlBoolean` type.</span></span> <span data-ttu-id="12fb5-113">São fornecidas as propriedades `IsTrue`, `IsFalse`e `IsNull` para verificar o valor de um tipo `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="12fb5-113">The properties `IsTrue`, `IsFalse`, and `IsNull` are provided to check the value of a `SqlBoolean` type.</span></span>  
  
## <a name="operations-functions-and-null-values"></a><span data-ttu-id="12fb5-114">Operações, funções e valores NULL</span><span class="sxs-lookup"><span data-stu-id="12fb5-114">Operations, Functions, and NULL Values</span></span>  
 <span data-ttu-id="12fb5-115">Todos os operadores aritméticos (+,-, \* ,/,%), operadores de bit (~, & e |) e a maioria das funções retornarão NULL se qualquer um dos operandos ou argumentos de `SqlTypes` forem nulos.</span><span class="sxs-lookup"><span data-stu-id="12fb5-115">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, and |), and most functions return NULL if any of the operands or arguments of `SqlTypes` are NULL.</span></span> <span data-ttu-id="12fb5-116">A propriedade `IsNull` sempre retorna um valor true ou false.</span><span class="sxs-lookup"><span data-stu-id="12fb5-116">The `IsNull` property always returns a true or false value.</span></span>  
  
## <a name="precision"></a><span data-ttu-id="12fb5-117">Precisão</span><span class="sxs-lookup"><span data-stu-id="12fb5-117">Precision</span></span>  
 <span data-ttu-id="12fb5-118">Tipos de dados decimais no CLR [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] têm valores máximos diferentes em relação aos tipos de dados numéricos e decimais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12fb5-118">Decimal data types in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR have different maximum values than those of the numeric and decimal data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="12fb5-119">Além disso, no CLR [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], tipos de dados decimais supõem a precisão máxima.</span><span class="sxs-lookup"><span data-stu-id="12fb5-119">In addition, in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR decimal data types assume the maximum precision.</span></span> <span data-ttu-id="12fb5-120">No CLR do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], no entanto, `SqlDecimal` fornece a mesma precisão e escala máximas, além da mesma semântica do tipo de dados decimal do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12fb5-120">In the CLR for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], however, `SqlDecimal` provides the same maximum precision and scale, and the same semantics as the decimal data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="overflow-detection"></a><span data-ttu-id="12fb5-121">Detecção de estouro</span><span class="sxs-lookup"><span data-stu-id="12fb5-121">Overflow Detection</span></span>  
 <span data-ttu-id="12fb5-122">No CLR [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], a adição de dois números muito grandes pode não lançar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="12fb5-122">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, the addition of two very large numbers may not throw an exception.</span></span> <span data-ttu-id="12fb5-123">Na verdade, caso nenhum operador de verificação tenha sido usado, o resultado retornado pode ser "delimitado" como um inteiro negativo.</span><span class="sxs-lookup"><span data-stu-id="12fb5-123">Instead, if no check operator has been used, the returned result may "wrap around" as a negative integer.</span></span> <span data-ttu-id="12fb5-124">Em `System.Data.SqlTypes`, são lançadas exceções para todos os estouros e erros de estouro, além de erros de divisão por zero.</span><span class="sxs-lookup"><span data-stu-id="12fb5-124">In `System.Data.SqlTypes`, exceptions are thrown for all overflow and underflow errors, and divide-by-zero errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fb5-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12fb5-125">See Also</span></span>  
 [<span data-ttu-id="12fb5-126">Tipos de dados do SQL Server no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="12fb5-126">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
