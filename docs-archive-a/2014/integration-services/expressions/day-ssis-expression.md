---
title: DAY (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DAY function
- dates [Integration Services], DAY
ms.assetid: d8447187-49df-45b7-a98e-142ad44fd3e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b7acac3f3949cbbd07adbe6382ea3d875f94cb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680572"
---
# <a name="day-ssis-expression"></a><span data-ttu-id="18ed5-102">DAY (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="18ed5-102">DAY (SSIS Expression)</span></span>
  <span data-ttu-id="18ed5-103">Retorna um inteiro que representa a parte do dia em uma data.</span><span class="sxs-lookup"><span data-stu-id="18ed5-103">Returns an integer that represents the day datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ed5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="18ed5-104">Syntax</span></span>  
  
```  
  
DAY(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="18ed5-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="18ed5-105">Arguments</span></span>  
 <span data-ttu-id="18ed5-106">*date*</span><span class="sxs-lookup"><span data-stu-id="18ed5-106">*date*</span></span>  
 <span data-ttu-id="18ed5-107">É uma expressão que retorna uma data válida ou uma cadeia de caracteres em formato de data.</span><span class="sxs-lookup"><span data-stu-id="18ed5-107">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="18ed5-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="18ed5-108">Result Types</span></span>  
 <span data-ttu-id="18ed5-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="18ed5-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18ed5-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="18ed5-110">Remarks</span></span>  
 <span data-ttu-id="18ed5-111">DAY retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="18ed5-111">DAY returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="18ed5-112">Um literal de data deve ser convertido explicitamente em um dos tipos de dados de data.</span><span class="sxs-lookup"><span data-stu-id="18ed5-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="18ed5-113">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="18ed5-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18ed5-114">A expressão não é validada quando um literal de data é convertido explicitamente em um destes tipos de dados de data: DT_DBTIMESTAMPOFFSET e DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="18ed5-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="18ed5-115">A função DAY é mais resumida, mas equivale a usar a DATEPART ("Dia", data).</span><span class="sxs-lookup"><span data-stu-id="18ed5-115">Using the DAY function is briefer but equivalent to using DATEPART("Day", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="18ed5-116">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="18ed5-116">Expression Examples</span></span>  
 <span data-ttu-id="18ed5-117">Este exemplo retorna o número do dia em um literal de data.</span><span class="sxs-lookup"><span data-stu-id="18ed5-117">This example returns the number of the day in a date literal.</span></span> <span data-ttu-id="18ed5-118">Se a data estiver no formato "mm/dd/aaaa", este exemplo retornará 23.</span><span class="sxs-lookup"><span data-stu-id="18ed5-118">If the date format is in "mm/dd/yyyy" format, this example returns 23.</span></span>  
  
```  
DAY((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="18ed5-119">Este exemplo retorna o inteiro que representa o dia na coluna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="18ed5-119">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DAY(ModifiedDate)  
```  
  
 <span data-ttu-id="18ed5-120">Este exemplo retorna o inteiro que representa o dia da data atual.</span><span class="sxs-lookup"><span data-stu-id="18ed5-120">This example returns the integer that represents the day of the current date.</span></span>  
  
```  
DAY(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="18ed5-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18ed5-121">See Also</span></span>  
 <span data-ttu-id="18ed5-122">[DATEADD &#40;Expressão do SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="18ed5-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="18ed5-123">[DATEDIFF &#40;Expressão do SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="18ed5-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="18ed5-124">[DATEPART &#40;Expressão do SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="18ed5-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="18ed5-125">[MONTH &#40;Expressão do SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="18ed5-125">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="18ed5-126">[YEAR &#40;Expressão do SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="18ed5-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="18ed5-127">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="18ed5-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
