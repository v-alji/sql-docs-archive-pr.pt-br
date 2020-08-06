---
title: DATEPART (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEPART
- DATEPART function
ms.assetid: 3e590094-fc49-4144-805f-fdc1bf2fe509
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aed7146c74c6738ba979f422bd65b7e1b539e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680574"
---
# <a name="datepart-ssis-expression"></a><span data-ttu-id="4790a-102">DATEPART (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="4790a-102">DATEPART (SSIS Expression)</span></span>
  <span data-ttu-id="4790a-103">Retorna um inteiro que representa uma parte de uma data.</span><span class="sxs-lookup"><span data-stu-id="4790a-103">Returns an integer representing a datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4790a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4790a-104">Syntax</span></span>  
  
```  
  
DATEPART(datepart, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="4790a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4790a-105">Arguments</span></span>  
 <span data-ttu-id="4790a-106">*datepart*</span><span class="sxs-lookup"><span data-stu-id="4790a-106">*datepart*</span></span>  
 <span data-ttu-id="4790a-107">É o parâmetro que especifica para qual parte da data retornar um valor novo.</span><span class="sxs-lookup"><span data-stu-id="4790a-107">Is the parameter that specifies for which part of the date to return a new value.</span></span>  
  
 <span data-ttu-id="4790a-108">*date*</span><span class="sxs-lookup"><span data-stu-id="4790a-108">*date*</span></span>  
 <span data-ttu-id="4790a-109">É uma expressão que retorna uma data válida ou uma cadeia de caracteres em formato de data.</span><span class="sxs-lookup"><span data-stu-id="4790a-109">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4790a-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="4790a-110">Result Types</span></span>  
 <span data-ttu-id="4790a-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="4790a-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4790a-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="4790a-112">Remarks</span></span>  
 <span data-ttu-id="4790a-113">DATEPART retorna um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="4790a-113">DATEPART returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="4790a-114">Um literal de data deve ser convertido explicitamente em um dos tipos de dados de data.</span><span class="sxs-lookup"><span data-stu-id="4790a-114">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="4790a-115">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="4790a-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="4790a-116">A tabela a seguir lista as partes de data e as abreviações reconhecidas pelo avaliador de expressão.</span><span class="sxs-lookup"><span data-stu-id="4790a-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="4790a-117">Os nomes das partes da data não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4790a-117">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="4790a-118">datepart</span><span class="sxs-lookup"><span data-stu-id="4790a-118">Datepart</span></span>|<span data-ttu-id="4790a-119">Abreviações</span><span class="sxs-lookup"><span data-stu-id="4790a-119">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="4790a-120">Ano</span><span class="sxs-lookup"><span data-stu-id="4790a-120">Year</span></span>|<span data-ttu-id="4790a-121">aa, aaaa</span><span class="sxs-lookup"><span data-stu-id="4790a-121">yy, yyyy</span></span>|  
|<span data-ttu-id="4790a-122">Quarter</span><span class="sxs-lookup"><span data-stu-id="4790a-122">Quarter</span></span>|<span data-ttu-id="4790a-123">qq, q</span><span class="sxs-lookup"><span data-stu-id="4790a-123">qq, q</span></span>|  
|<span data-ttu-id="4790a-124">Month</span><span class="sxs-lookup"><span data-stu-id="4790a-124">Month</span></span>|<span data-ttu-id="4790a-125">mm, m</span><span class="sxs-lookup"><span data-stu-id="4790a-125">mm, m</span></span>|  
|<span data-ttu-id="4790a-126">Dia do ano</span><span class="sxs-lookup"><span data-stu-id="4790a-126">Dayofyear</span></span>|<span data-ttu-id="4790a-127">dy, y</span><span class="sxs-lookup"><span data-stu-id="4790a-127">dy, y</span></span>|  
|<span data-ttu-id="4790a-128">Dia</span><span class="sxs-lookup"><span data-stu-id="4790a-128">Day</span></span>|<span data-ttu-id="4790a-129">dd, d</span><span class="sxs-lookup"><span data-stu-id="4790a-129">dd, d</span></span>|  
|<span data-ttu-id="4790a-130">Semana</span><span class="sxs-lookup"><span data-stu-id="4790a-130">Week</span></span>|<span data-ttu-id="4790a-131">wk, ww</span><span class="sxs-lookup"><span data-stu-id="4790a-131">wk, ww</span></span>|  
|<span data-ttu-id="4790a-132">Weekday</span><span class="sxs-lookup"><span data-stu-id="4790a-132">Weekday</span></span>|<span data-ttu-id="4790a-133">dw</span><span class="sxs-lookup"><span data-stu-id="4790a-133">dw</span></span>|  
|<span data-ttu-id="4790a-134">Hora</span><span class="sxs-lookup"><span data-stu-id="4790a-134">Hour</span></span>|<span data-ttu-id="4790a-135">Hh</span><span class="sxs-lookup"><span data-stu-id="4790a-135">Hh</span></span>|  
|<span data-ttu-id="4790a-136">Minuto</span><span class="sxs-lookup"><span data-stu-id="4790a-136">Minute</span></span>|<span data-ttu-id="4790a-137">mi, n</span><span class="sxs-lookup"><span data-stu-id="4790a-137">mi, n</span></span>|  
|<span data-ttu-id="4790a-138">Segundo</span><span class="sxs-lookup"><span data-stu-id="4790a-138">Second</span></span>|<span data-ttu-id="4790a-139">ss, s</span><span class="sxs-lookup"><span data-stu-id="4790a-139">ss, s</span></span>|  
|<span data-ttu-id="4790a-140">Milissegundos</span><span class="sxs-lookup"><span data-stu-id="4790a-140">Millisecond</span></span>|<span data-ttu-id="4790a-141">Ms</span><span class="sxs-lookup"><span data-stu-id="4790a-141">Ms</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="4790a-142">Exemplos de expressões SSIS</span><span class="sxs-lookup"><span data-stu-id="4790a-142">SSIS Expression Examples</span></span>  
 <span data-ttu-id="4790a-143">Este exemplo retorna o inteiro que representa o mês em um literal de data.</span><span class="sxs-lookup"><span data-stu-id="4790a-143">This example returns the integer that represents the month in a date literal.</span></span> <span data-ttu-id="4790a-144">Se a data estiver em formato mm/dd/aaaa", este exemplo retornará 11.</span><span class="sxs-lookup"><span data-stu-id="4790a-144">If the date is in mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
DATEPART("month", (DT_DBTIMESTAMP)"11/04/2002")  
```  
  
 <span data-ttu-id="4790a-145">Este exemplo retorna o inteiro que representa o dia na coluna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="4790a-145">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DATEPART("dd", ModifiedDate)  
```  
  
 <span data-ttu-id="4790a-146">Este exemplo retorna o inteiro que representa o ano da data atual.</span><span class="sxs-lookup"><span data-stu-id="4790a-146">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
DATEPART("yy",GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="4790a-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4790a-147">See Also</span></span>  
 <span data-ttu-id="4790a-148">[DATEADD &#40;Expressão do SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4790a-148">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="4790a-149">[DATEDIFF &#40;Expressão do SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4790a-149">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="4790a-150">[DAY &#40;Expressão do SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4790a-150">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="4790a-151">[MONTH &#40;Expressão do SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4790a-151">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="4790a-152">[YEAR &#40;Expressão do SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4790a-152">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="4790a-153">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4790a-153">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
