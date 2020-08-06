---
title: DATEDIFF (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DATEDIFF statement
- dates [Integration Services], DATEDIFF
ms.assetid: 449b327f-47c7-4709-8bc6-4ee9a35cc330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33edf2a152f70bb8c5bbd1f69cb87354e099b246
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680576"
---
# <a name="datediff-ssis-expression"></a><span data-ttu-id="998dd-102">DATEDIFF (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="998dd-102">DATEDIFF (SSIS Expression)</span></span>
  <span data-ttu-id="998dd-103">Retorna o número de limites de data e hora entre duas datas especificadas.</span><span class="sxs-lookup"><span data-stu-id="998dd-103">Returns the number of date and time boundaries crossed between two specified dates.</span></span> <span data-ttu-id="998dd-104">O parâmetro *datepart* identifica quais limites de data e hora serão comparados.</span><span class="sxs-lookup"><span data-stu-id="998dd-104">The *datepart* parameter identifies which date and time boundaries to compare.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="998dd-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="998dd-105">Syntax</span></span>  
  
```  
  
DATEDIFF(datepart, startdate, endate)  
```  
  
## <a name="arguments"></a><span data-ttu-id="998dd-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="998dd-106">Arguments</span></span>  
 <span data-ttu-id="998dd-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="998dd-107">*datepart*</span></span>  
 <span data-ttu-id="998dd-108">É o parâmetro que especifica qual parte da data será comparada e para a qual um valor será retornado.</span><span class="sxs-lookup"><span data-stu-id="998dd-108">Is the parameter that specifies which part of the date to compare and return a value for.</span></span>  
  
 <span data-ttu-id="998dd-109">*startdate*</span><span class="sxs-lookup"><span data-stu-id="998dd-109">*startdate*</span></span>  
 <span data-ttu-id="998dd-110">É a data de início do intervalo.</span><span class="sxs-lookup"><span data-stu-id="998dd-110">Is the start date of the interval.</span></span>  
  
 <span data-ttu-id="998dd-111">*endate*</span><span class="sxs-lookup"><span data-stu-id="998dd-111">*endate*</span></span>  
 <span data-ttu-id="998dd-112">É a data de término do intervalo.</span><span class="sxs-lookup"><span data-stu-id="998dd-112">Is the end date of the interval.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="998dd-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="998dd-113">Result Types</span></span>  
 <span data-ttu-id="998dd-114">DT_I4</span><span class="sxs-lookup"><span data-stu-id="998dd-114">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="998dd-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="998dd-115">Remarks</span></span>  
 <span data-ttu-id="998dd-116">A tabela a seguir lista as partes de data e as abreviações reconhecidas pelo avaliador de expressão.</span><span class="sxs-lookup"><span data-stu-id="998dd-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span>  
  
|<span data-ttu-id="998dd-117">datepart</span><span class="sxs-lookup"><span data-stu-id="998dd-117">Datepart</span></span>|<span data-ttu-id="998dd-118">Abreviações</span><span class="sxs-lookup"><span data-stu-id="998dd-118">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="998dd-119">Ano</span><span class="sxs-lookup"><span data-stu-id="998dd-119">Year</span></span>|<span data-ttu-id="998dd-120">aa, aaaa</span><span class="sxs-lookup"><span data-stu-id="998dd-120">yy, yyyy</span></span>|  
|<span data-ttu-id="998dd-121">Quarter</span><span class="sxs-lookup"><span data-stu-id="998dd-121">Quarter</span></span>|<span data-ttu-id="998dd-122">qq, q</span><span class="sxs-lookup"><span data-stu-id="998dd-122">qq, q</span></span>|  
|<span data-ttu-id="998dd-123">Month</span><span class="sxs-lookup"><span data-stu-id="998dd-123">Month</span></span>|<span data-ttu-id="998dd-124">mm, m</span><span class="sxs-lookup"><span data-stu-id="998dd-124">mm, m</span></span>|  
|<span data-ttu-id="998dd-125">Dia do ano</span><span class="sxs-lookup"><span data-stu-id="998dd-125">Dayofyear</span></span>|<span data-ttu-id="998dd-126">dy, y</span><span class="sxs-lookup"><span data-stu-id="998dd-126">dy, y</span></span>|  
|<span data-ttu-id="998dd-127">Dia</span><span class="sxs-lookup"><span data-stu-id="998dd-127">Day</span></span>|<span data-ttu-id="998dd-128">dd, d</span><span class="sxs-lookup"><span data-stu-id="998dd-128">dd, d</span></span>|  
|<span data-ttu-id="998dd-129">Semana</span><span class="sxs-lookup"><span data-stu-id="998dd-129">Week</span></span>|<span data-ttu-id="998dd-130">wk, ww</span><span class="sxs-lookup"><span data-stu-id="998dd-130">wk, ww</span></span>|  
|<span data-ttu-id="998dd-131">Weekday</span><span class="sxs-lookup"><span data-stu-id="998dd-131">Weekday</span></span>|<span data-ttu-id="998dd-132">dw, w</span><span class="sxs-lookup"><span data-stu-id="998dd-132">dw, w</span></span>|  
|<span data-ttu-id="998dd-133">Hora</span><span class="sxs-lookup"><span data-stu-id="998dd-133">Hour</span></span>|<span data-ttu-id="998dd-134">Hh</span><span class="sxs-lookup"><span data-stu-id="998dd-134">Hh</span></span>|  
|<span data-ttu-id="998dd-135">Minuto</span><span class="sxs-lookup"><span data-stu-id="998dd-135">Minute</span></span>|<span data-ttu-id="998dd-136">mi, n</span><span class="sxs-lookup"><span data-stu-id="998dd-136">mi, n</span></span>|  
|<span data-ttu-id="998dd-137">Segundo</span><span class="sxs-lookup"><span data-stu-id="998dd-137">Second</span></span>|<span data-ttu-id="998dd-138">ss, s</span><span class="sxs-lookup"><span data-stu-id="998dd-138">ss, s</span></span>|  
|<span data-ttu-id="998dd-139">Milissegundos</span><span class="sxs-lookup"><span data-stu-id="998dd-139">Millisecond</span></span>|<span data-ttu-id="998dd-140">Ms</span><span class="sxs-lookup"><span data-stu-id="998dd-140">Ms</span></span>|  
  
 <span data-ttu-id="998dd-141">DATEDIFF retornará um resultado nulo se qualquer argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="998dd-141">DATEDIFF returns a null result if any argument is null.</span></span>  
  
 <span data-ttu-id="998dd-142">Um literal de data deve ser convertido explicitamente em um dos tipos de dados de data.</span><span class="sxs-lookup"><span data-stu-id="998dd-142">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="998dd-143">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="998dd-143">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="998dd-144">Ocorrerá um erro se uma data não for válida, se a unidade de data ou hora não for uma cadeia de caracteres, se a data de início não for uma data ou se a data de término não for uma data.</span><span class="sxs-lookup"><span data-stu-id="998dd-144">An error occurs if a date is not valid, if the date or time unit is not a string, if the start date is not a date, or if the end date is not a date.</span></span>  
  
 <span data-ttu-id="998dd-145">Se a data de término for anterior à data de início, a função retornará um número negativo.</span><span class="sxs-lookup"><span data-stu-id="998dd-145">If the end date is earlier than the start date, the function returns a negative number.</span></span> <span data-ttu-id="998dd-146">Se as datas de início e término forem iguais ou estiverem dentro do mesmo intervalo, a função retornará zero.</span><span class="sxs-lookup"><span data-stu-id="998dd-146">If the start and end dates are equal or fall within the same interval, the function returns zero.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="998dd-147">Exemplos de expressões SSIS</span><span class="sxs-lookup"><span data-stu-id="998dd-147">SSIS Expression Examples</span></span>  
 <span data-ttu-id="998dd-148">Este exemplo calcula o número de dias entre dois literals de data.</span><span class="sxs-lookup"><span data-stu-id="998dd-148">This example calculates the number of days between two date literals.</span></span> <span data-ttu-id="998dd-149">Se a data estiver no formato "mm/dd/aaaa", a função retornará 7.</span><span class="sxs-lookup"><span data-stu-id="998dd-149">If the date is in "mm/dd/yyyy" format, the function returns 7.</span></span>  
  
```  
DATEDIFF("dd", (DT_DBTIMESTAMP)"8/1/2003", (DT_DBTIMESTAMP)"8/8/2003")  
```  
  
 <span data-ttu-id="998dd-150">Este exemplo retorna o número de meses entre um literal de data e a data atual.</span><span class="sxs-lookup"><span data-stu-id="998dd-150">This example returns the number of months between a date literal and the current date.</span></span>  
  
```  
DATEDIFF("mm", (DT_DBTIMESTAMP)"8/1/2003",GETDATE())  
```  
  
 <span data-ttu-id="998dd-151">Este exemplo retorna o número de semanas entre a data na coluna **ModifiedDate** e a variável **YearEndDate** .</span><span class="sxs-lookup"><span data-stu-id="998dd-151">This example returns the number of weeks between the date in the **ModifiedDate** column and the **YearEndDate** variable.</span></span> <span data-ttu-id="998dd-152">Se **YearEndDate** tiver um `date` tipo de dados, nenhuma conversão explícita será necessária.</span><span class="sxs-lookup"><span data-stu-id="998dd-152">If **YearEndDate** has a `date` data type, no explicit casting is required.</span></span>  
  
```  
DATEDIFF("Week", ModifiedDate,@YearEndDate)  
```  
  
## <a name="see-also"></a><span data-ttu-id="998dd-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="998dd-153">See Also</span></span>  
 <span data-ttu-id="998dd-154">[DATEADD &#40;Expressão do SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="998dd-154">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="998dd-155">[DATEPART &#40;Expressão do SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="998dd-155">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="998dd-156">[DAY &#40;Expressão do SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="998dd-156">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="998dd-157">[MONTH &#40;Expressão do SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="998dd-157">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="998dd-158">[YEAR &#40;Expressão do SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="998dd-158">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="998dd-159">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="998dd-159">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
