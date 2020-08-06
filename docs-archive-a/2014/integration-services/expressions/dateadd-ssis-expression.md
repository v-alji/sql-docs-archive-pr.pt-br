---
title: DATEADD (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEADD
- dates [Integration Services]
- DATEADD function
ms.assetid: fa5c37b1-2ddc-4857-8f8e-f6d5643b654f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9feb288318bdf9705928cb930f175f5c170c384e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683633"
---
# <a name="dateadd-ssis-expression"></a><span data-ttu-id="514e7-102">DATEADD (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="514e7-102">DATEADD (SSIS Expression)</span></span>
  <span data-ttu-id="514e7-103">Retorna um novo valor DT_DBTIMESTAMP depois de adicionar um número que representa um intervalo de data ou hora para a parte especificada na data.</span><span class="sxs-lookup"><span data-stu-id="514e7-103">Returns a new DT_DBTIMESTAMP value after adding a number that represents a date or time interval to the specified datepart in a date.</span></span> <span data-ttu-id="514e7-104">O parâmetro de número deve ser avaliado como um inteiro e o parâmetro de data deve ser avaliado como uma data válida.</span><span class="sxs-lookup"><span data-stu-id="514e7-104">The number parameter must evaluate to an integer, and the date parameter must evaluate to a valid date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="514e7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="514e7-105">Syntax</span></span>  
  
```  
  
DATEADD(datepart, number, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="514e7-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="514e7-106">Arguments</span></span>  
 <span data-ttu-id="514e7-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="514e7-107">*datepart*</span></span>  
 <span data-ttu-id="514e7-108">É o parâmetro que especifica à qual parte da data deve-se adicionar um número.</span><span class="sxs-lookup"><span data-stu-id="514e7-108">Is the parameter that specifies which part of the date to add a number to.</span></span>  
  
 <span data-ttu-id="514e7-109">*number*</span><span class="sxs-lookup"><span data-stu-id="514e7-109">*number*</span></span>  
 <span data-ttu-id="514e7-110">É o valor usado para incrementar *datepart*.</span><span class="sxs-lookup"><span data-stu-id="514e7-110">Is the value used to increment *datepart*.</span></span> <span data-ttu-id="514e7-111">O valor deve ser um valor inteiro conhecido quando a expressão é analisada.</span><span class="sxs-lookup"><span data-stu-id="514e7-111">The value must be an integer value that is known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="514e7-112">*date*</span><span class="sxs-lookup"><span data-stu-id="514e7-112">*date*</span></span>  
 <span data-ttu-id="514e7-113">É uma expressão que retorna uma data válida ou uma cadeia de caracteres em formato de data.</span><span class="sxs-lookup"><span data-stu-id="514e7-113">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="514e7-114">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="514e7-114">Result Types</span></span>  
 <span data-ttu-id="514e7-115">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="514e7-115">DT_DBTIMESTAMP</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="514e7-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="514e7-116">Remarks</span></span>  
 <span data-ttu-id="514e7-117">A tabela a seguir lista as partes de data e as abreviações reconhecidas pelo avaliador de expressão.</span><span class="sxs-lookup"><span data-stu-id="514e7-117">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="514e7-118">Os nomes das partes da data não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="514e7-118">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="514e7-119">datepart</span><span class="sxs-lookup"><span data-stu-id="514e7-119">Datepart</span></span>|<span data-ttu-id="514e7-120">Abreviações</span><span class="sxs-lookup"><span data-stu-id="514e7-120">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="514e7-121">Ano</span><span class="sxs-lookup"><span data-stu-id="514e7-121">Year</span></span>|<span data-ttu-id="514e7-122">aa, aaaa</span><span class="sxs-lookup"><span data-stu-id="514e7-122">yy, yyyy</span></span>|  
|<span data-ttu-id="514e7-123">Quarter</span><span class="sxs-lookup"><span data-stu-id="514e7-123">Quarter</span></span>|<span data-ttu-id="514e7-124">qq, q</span><span class="sxs-lookup"><span data-stu-id="514e7-124">qq, q</span></span>|  
|<span data-ttu-id="514e7-125">Month</span><span class="sxs-lookup"><span data-stu-id="514e7-125">Month</span></span>|<span data-ttu-id="514e7-126">mm, m</span><span class="sxs-lookup"><span data-stu-id="514e7-126">mm, m</span></span>|  
|<span data-ttu-id="514e7-127">Dia do ano</span><span class="sxs-lookup"><span data-stu-id="514e7-127">Dayofyear</span></span>|<span data-ttu-id="514e7-128">dy, y</span><span class="sxs-lookup"><span data-stu-id="514e7-128">dy, y</span></span>|  
|<span data-ttu-id="514e7-129">Dia</span><span class="sxs-lookup"><span data-stu-id="514e7-129">Day</span></span>|<span data-ttu-id="514e7-130">dd, d</span><span class="sxs-lookup"><span data-stu-id="514e7-130">dd, d</span></span>|  
|<span data-ttu-id="514e7-131">Semana</span><span class="sxs-lookup"><span data-stu-id="514e7-131">Week</span></span>|<span data-ttu-id="514e7-132">wk, ww</span><span class="sxs-lookup"><span data-stu-id="514e7-132">wk, ww</span></span>|  
|<span data-ttu-id="514e7-133">Weekday</span><span class="sxs-lookup"><span data-stu-id="514e7-133">Weekday</span></span>|<span data-ttu-id="514e7-134">dw, w</span><span class="sxs-lookup"><span data-stu-id="514e7-134">dw, w</span></span>|  
|<span data-ttu-id="514e7-135">Hora</span><span class="sxs-lookup"><span data-stu-id="514e7-135">Hour</span></span>|<span data-ttu-id="514e7-136">Hh</span><span class="sxs-lookup"><span data-stu-id="514e7-136">Hh</span></span>|  
|<span data-ttu-id="514e7-137">Minuto</span><span class="sxs-lookup"><span data-stu-id="514e7-137">Minute</span></span>|<span data-ttu-id="514e7-138">mi, n</span><span class="sxs-lookup"><span data-stu-id="514e7-138">mi, n</span></span>|  
|<span data-ttu-id="514e7-139">Segundo</span><span class="sxs-lookup"><span data-stu-id="514e7-139">Second</span></span>|<span data-ttu-id="514e7-140">ss, s</span><span class="sxs-lookup"><span data-stu-id="514e7-140">ss, s</span></span>|  
|<span data-ttu-id="514e7-141">Milissegundos</span><span class="sxs-lookup"><span data-stu-id="514e7-141">Millisecond</span></span>|<span data-ttu-id="514e7-142">Ms</span><span class="sxs-lookup"><span data-stu-id="514e7-142">Ms</span></span>|  
  
 <span data-ttu-id="514e7-143">O argumento *number* deve estar disponível quando a expressão é analisada.</span><span class="sxs-lookup"><span data-stu-id="514e7-143">The *number* argument must be available when the expression is parsed.</span></span> <span data-ttu-id="514e7-144">O argumento pode ser uma constante ou variável.</span><span class="sxs-lookup"><span data-stu-id="514e7-144">The argument can be a constant or a variable.</span></span> <span data-ttu-id="514e7-145">Você não pode usar valores de coluna porque os valores não são conhecidos quando a expressão é analisada.</span><span class="sxs-lookup"><span data-stu-id="514e7-145">You cannot use column values because the values are not known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="514e7-146">O argumento *datepart* deve estar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="514e7-146">The *datepart* argument must be enclosed by quotation marks.</span></span>  
  
 <span data-ttu-id="514e7-147">Um literal de data deve ser convertido explicitamente em um dos tipos de dados de data.</span><span class="sxs-lookup"><span data-stu-id="514e7-147">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="514e7-148">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="514e7-148">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="514e7-149">DATEADD retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="514e7-149">DATEADD returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="514e7-150">Ocorrerão erros se uma data for inválida, se a unidade de data ou hora não for uma cadeia de caracteres ou se o incremento não for um inteiro estático.</span><span class="sxs-lookup"><span data-stu-id="514e7-150">Errors occur if a date is invalid, if the date or time unit is not a string, or if the increment is not a static integer.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="514e7-151">Exemplos de expressões SSIS</span><span class="sxs-lookup"><span data-stu-id="514e7-151">SSIS Expression Examples</span></span>  
 <span data-ttu-id="514e7-152">Esse exemplo adiciona um mês à data atual.</span><span class="sxs-lookup"><span data-stu-id="514e7-152">This example adds one month to the current date.</span></span>  
  
```  
DATEADD("Month", 1,GETDATE())  
```  
  
 <span data-ttu-id="514e7-153">Esse exemplo adiciona 21 dias às datas na coluna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="514e7-153">This example adds 21 days to the dates in the **ModifiedDate** column.</span></span>  
  
```  
DATEADD("day", 21, ModifiedDate)  
```  
  
 <span data-ttu-id="514e7-154">Esse exemplo adiciona 2 anos a uma data literal.</span><span class="sxs-lookup"><span data-stu-id="514e7-154">This example adds 2 years to a literal date.</span></span>  
  
```  
DATEADD("yyyy", 2, (DT_DBTIMESTAMP)"8/6/2003")  
```  
  
## <a name="see-also"></a><span data-ttu-id="514e7-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="514e7-155">See Also</span></span>  
 <span data-ttu-id="514e7-156">[DATEDIFF &#40;Expressão do SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="514e7-156">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="514e7-157">[DATEPART &#40;Expressão do SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="514e7-157">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="514e7-158">[DAY &#40;Expressão do SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="514e7-158">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="514e7-159">[MONTH &#40;Expressão do SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="514e7-159">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="514e7-160">[YEAR &#40;Expressão do SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="514e7-160">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="514e7-161">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="514e7-161">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
