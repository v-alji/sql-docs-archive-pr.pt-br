---
title: Formatos de data e hora | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- time data types [Integration Services]
- fast parse [Integration Services]
- date data types
- date and time formats for fast parse
ms.assetid: bed6e2c1-791a-4fa1-b29f-cbfdd1fa8d39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e6c461c0cfed6a776875831a46c94c70d895ba3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570776"
---
# <a name="date-and-time-formats"></a><span data-ttu-id="ac7f6-102">Formatos de data e hora</span><span class="sxs-lookup"><span data-stu-id="ac7f6-102">Date and Time Formats</span></span>
  <span data-ttu-id="ac7f6-103">A análise rápida fornece um conjunto de rotinas simples e rápidas para analisar dados.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-103">Fast parse provides a fast, simple set of routines for parsing data.</span></span> <span data-ttu-id="ac7f6-104">A análise rápida oferece suporte aos seguintes formatos de tipos de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-104">Fast parse supports the following formats for date and time data types.</span></span>  
  
## <a name="date-data-types"></a><span data-ttu-id="ac7f6-105">Tipos de dados de data</span><span class="sxs-lookup"><span data-stu-id="ac7f6-105">Date Data Types</span></span>  
 <span data-ttu-id="ac7f6-106">A análise rápida oferece suporte aos seguintes formatos de cadeia de caracteres para dados de data:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-106">Fast parse supports the following string formats for date data:</span></span>  
  
-   <span data-ttu-id="ac7f6-107">Formatos de data que incluem espaços em branco à esquerda.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-107">Date formats that include leading white spaces.</span></span> <span data-ttu-id="ac7f6-108">Por exemplo, o valor " 2004- 02-03" é válido.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-108">For example, the value " 2004- 02-03" is valid.</span></span>  
  
-   <span data-ttu-id="ac7f6-109">Os formatos ISO 8601, como listados na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-109">ISO 8601 formats, as listed in the following table:</span></span>  
  
    |<span data-ttu-id="ac7f6-110">Formatar</span><span class="sxs-lookup"><span data-stu-id="ac7f6-110">Format</span></span>|<span data-ttu-id="ac7f6-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac7f6-111">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="ac7f6-112">AAAAMMDD</span><span class="sxs-lookup"><span data-stu-id="ac7f6-112">YYYYMMDD</span></span><br /><br /> <span data-ttu-id="ac7f6-113">AAAA-MM-DD</span><span class="sxs-lookup"><span data-stu-id="ac7f6-113">YYYY-MM-DD</span></span>|<span data-ttu-id="ac7f6-114">Os formatos básico e estendido para um ano de quatro dígitos, um mês de dois dígitos e um dia de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-114">Basic and extended formats for a four-digit year, a two-digit month, and a two-digit day.</span></span> <span data-ttu-id="ac7f6-115">No formato estendido, as datas são separadas por um hífen (-).</span><span class="sxs-lookup"><span data-stu-id="ac7f6-115">In the extended format, the date parts are separated by a hyphen (-).</span></span>|  
    |<span data-ttu-id="ac7f6-116">AAAA-MM</span><span class="sxs-lookup"><span data-stu-id="ac7f6-116">YYYY-MM</span></span>|<span data-ttu-id="ac7f6-117">Os formatos básico e estendido de precisão reduzida para um ano de quatro dígitos e um mês de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-117">Basic and extended reduced precision formats for a four-digit year and a two-digit month.</span></span> <span data-ttu-id="ac7f6-118">No formato estendido, as datas são separadas por um hífen (-).</span><span class="sxs-lookup"><span data-stu-id="ac7f6-118">In the extended format, the date parts are separated by a hyphen (-).</span></span>|  
    |<span data-ttu-id="ac7f6-119">AAAA</span><span class="sxs-lookup"><span data-stu-id="ac7f6-119">YYYY</span></span>|<span data-ttu-id="ac7f6-120">O formato de precisão reduzida é um ano de quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-120">Reduced precision format is a four-digit year.</span></span>|  
  
 <span data-ttu-id="ac7f6-121">A análise rápida não oferece suporte aos seguintes formatos para dados de data:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-121">Fast parse does not support the following formats for date data:</span></span>  
  
-   <span data-ttu-id="ac7f6-122">Valores de meses alfabéticos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-122">Alphabetical month values.</span></span> <span data-ttu-id="ac7f6-123">Por exemplo, o formato de data Oct-31-2003 não é válido.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-123">For example, the date format Oct-31-2003 is not valid.</span></span>  
  
-   <span data-ttu-id="ac7f6-124">Formatos ambíguos como DD-MM-AAAA e MM-DD-AAAA.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-124">Ambiguous formats such as DD-MM-YYYY and MM-DD-YYYY.</span></span> <span data-ttu-id="ac7f6-125">Por exemplo, as datas 03-04-1995 e 04-03-1995  não são válidas.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-125">For example, the dates 03-04-1995 and 04-03-1995 are not valid.</span></span>  
  
-   <span data-ttu-id="ac7f6-126">Os formatos básico e estendido truncados para um ano de calendário de quatro dígitos e um dia de três dígitos em um ano, AAAADDD e AAAA-DDD.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-126">Basic and extended truncated formats for a four-digit calendar year and a three-digit day within a year, YYYYDDD and YYYY-DDD.</span></span>  
  
-   <span data-ttu-id="ac7f6-127">Os formatos básico e estendido para um ano de quatro dígitos, um número de dois dígitos para a semana do ano e um número de um dígito para o dia da semana, AAAASssD e AAAA-Sss-D.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-127">Basic and extended formats for a four-digit year, a two-digit number for the week of the year, and a one-digit number for the day of the week, YYYYWwwD and YYYY-Www-D</span></span>  
  
-   <span data-ttu-id="ac7f6-128">Os formatos básico e estendido truncados para uma data de um ano e semana são um ano de quatro dígitos e um número de dois dígitos para a semana, AAASss e AAAA-Sss.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-128">Basic and extended truncated formats for a year and week date are a four-digit year and a two-digit number for the week, YYYWww and YYYY-Www</span></span>  
  
 <span data-ttu-id="ac7f6-129">A análise efetua a saída dos dados como DT_DBDATE.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-129">Fast parse outputs the data as DT_DBDATE.</span></span> <span data-ttu-id="ac7f6-130">Os valores de data em formatos truncados são convertidos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-130">Date values in truncated formats are padded.</span></span> <span data-ttu-id="ac7f6-131">Por exemplo, AAAA se torna AAAA0101.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-131">For example, YYYY becomes YYYY0101.</span></span>  
  
 <span data-ttu-id="ac7f6-132">Para obter mais informações, consulte [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac7f6-132">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="time-data-type"></a><span data-ttu-id="ac7f6-133">Tipo de dados de hora</span><span class="sxs-lookup"><span data-stu-id="ac7f6-133">Time Data Type</span></span>  
 <span data-ttu-id="ac7f6-134">A análise rápida oferece suporte aos seguintes formatos de cadeia de caracteres para dados de hora:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-134">Fast parse supports the following string formats for time data:</span></span>  
  
-   <span data-ttu-id="ac7f6-135">Formatos de hora que incluem espaços em branco à esquerda.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-135">Time formats that include leading white spaces.</span></span> <span data-ttu-id="ac7f6-136">Por exemplo, o valor " 10:24" é válido.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-136">For example, the value " 10:24" is valid.</span></span>  
  
-   <span data-ttu-id="ac7f6-137">Formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-137">24-hour format.</span></span> <span data-ttu-id="ac7f6-138">A análise rápida não oferece suporte à notação AM e PM.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-138">Fast parse does not support the AM and PM notation.</span></span>  
  
-   <span data-ttu-id="ac7f6-139">Os formatos de hora ISO 8601, como listados na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-139">ISO 8601 time formats, as listed in the following table:</span></span>  
  
    |<span data-ttu-id="ac7f6-140">Formatar</span><span class="sxs-lookup"><span data-stu-id="ac7f6-140">Format</span></span>|<span data-ttu-id="ac7f6-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac7f6-141">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="ac7f6-142">HHMISS</span><span class="sxs-lookup"><span data-stu-id="ac7f6-142">HHMISS</span></span><br /><br /> <span data-ttu-id="ac7f6-143">HH:MI:SS</span><span class="sxs-lookup"><span data-stu-id="ac7f6-143">HH:MI:SS</span></span>|<span data-ttu-id="ac7f6-144">Os formatos básico e estendido para uma hora de dois dígitos, um minuto de dois dígitos e um segundo de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-144">Basic and extended formats for a two-digit hour, a two-digit minute, and a two-digit second.</span></span> <span data-ttu-id="ac7f6-145">No formato estendido, a hora é separada por dois pontos (:).</span><span class="sxs-lookup"><span data-stu-id="ac7f6-145">In the extended format, the time parts are separated by a colon (:).</span></span>|  
    |<span data-ttu-id="ac7f6-146">HHMI</span><span class="sxs-lookup"><span data-stu-id="ac7f6-146">HHMI</span></span><br /><br /> <span data-ttu-id="ac7f6-147">HH:MI</span><span class="sxs-lookup"><span data-stu-id="ac7f6-147">HH:MI</span></span>|<span data-ttu-id="ac7f6-148">Os formatos básico e estendido truncados para uma hora de dois dígitos e um minuto de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-148">Basic and extended truncated format for a two-digit hour and a two-digit minute.</span></span> <span data-ttu-id="ac7f6-149">No formato estendido, a hora é separada por dois pontos (:).</span><span class="sxs-lookup"><span data-stu-id="ac7f6-149">In the extended format, the time parts are separated by a colon (:).</span></span>|  
    |<span data-ttu-id="ac7f6-150">HH</span><span class="sxs-lookup"><span data-stu-id="ac7f6-150">HH</span></span>|<span data-ttu-id="ac7f6-151">Formato truncado para uma hora de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-151">Truncated format for a two-digit hour.</span></span>|  
    |<span data-ttu-id="ac7f6-152">00:00:00</span><span class="sxs-lookup"><span data-stu-id="ac7f6-152">00:00:00</span></span><br /><br /> <span data-ttu-id="ac7f6-153">000000</span><span class="sxs-lookup"><span data-stu-id="ac7f6-153">000000</span></span><br /><br /> <span data-ttu-id="ac7f6-154">0000</span><span class="sxs-lookup"><span data-stu-id="ac7f6-154">0000</span></span><br /><br /> <span data-ttu-id="ac7f6-155">00</span><span class="sxs-lookup"><span data-stu-id="ac7f6-155">00</span></span><br /><br /> <span data-ttu-id="ac7f6-156">240000</span><span class="sxs-lookup"><span data-stu-id="ac7f6-156">240000</span></span><br /><br /> <span data-ttu-id="ac7f6-157">24:00:00</span><span class="sxs-lookup"><span data-stu-id="ac7f6-157">24:00:00</span></span><br /><br /> <span data-ttu-id="ac7f6-158">2400</span><span class="sxs-lookup"><span data-stu-id="ac7f6-158">2400</span></span><br /><br /> <span data-ttu-id="ac7f6-159">24</span><span class="sxs-lookup"><span data-stu-id="ac7f6-159">24</span></span>|<span data-ttu-id="ac7f6-160">O formato para meia-noite.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-160">The format for midnight.</span></span>|  
  
-   <span data-ttu-id="ac7f6-161">Os formatos de hora que especificam um fuso horário, como listados na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-161">Time formats that specify a time zone, as listed in the following table:.</span></span>  
  
    |<span data-ttu-id="ac7f6-162">Formatar</span><span class="sxs-lookup"><span data-stu-id="ac7f6-162">Format</span></span>|<span data-ttu-id="ac7f6-163">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac7f6-163">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="ac7f6-164">+HH:MI</span><span class="sxs-lookup"><span data-stu-id="ac7f6-164">+HH:MI</span></span><br /><br /> <span data-ttu-id="ac7f6-165">+HHMI</span><span class="sxs-lookup"><span data-stu-id="ac7f6-165">+HHMI</span></span>|<span data-ttu-id="ac7f6-166">Os formatos básico e estendido que indicam o número de horas e minutos que são adicionados ao tempo universal coordenado (UTC) para obter a hora local.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-166">Basic and extended formats that indicate the number of hours and minutes that are added to Coordinated Universal Time (UTC) to obtain the local time.</span></span>|  
    |<span data-ttu-id="ac7f6-167">-HH:MI</span><span class="sxs-lookup"><span data-stu-id="ac7f6-167">-HH:MI</span></span><br /><br /> <span data-ttu-id="ac7f6-168">-HHMI</span><span class="sxs-lookup"><span data-stu-id="ac7f6-168">-HHMI</span></span>|<span data-ttu-id="ac7f6-169">Os formatos básico e estendido que indicam o número de horas e minutos que são subtraídos do UTC para obter a hora local.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-169">Basic and extended formats that indicate the number of hours and minutes that are subtracted from UTC to obtain the local time.</span></span>|  
    |<span data-ttu-id="ac7f6-170">+HH</span><span class="sxs-lookup"><span data-stu-id="ac7f6-170">+HH</span></span>|<span data-ttu-id="ac7f6-171">O formato truncado que indica o número de horas que são adicionadas ao UTC para obter a hora local.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-171">Truncated format that indicates the number of hours that are added to UTC to obtain the local time.</span></span>|  
    |<span data-ttu-id="ac7f6-172">-HH</span><span class="sxs-lookup"><span data-stu-id="ac7f6-172">-HH</span></span>|<span data-ttu-id="ac7f6-173">O formato truncado que indica o número de horas que são subtraídas do UTC para obter a hora local.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-173">Truncated format that indicates the number of hours that are subtracted from UTC to obtain the local time.</span></span>|  
    |<span data-ttu-id="ac7f6-174">Z</span><span class="sxs-lookup"><span data-stu-id="ac7f6-174">Z</span></span>|<span data-ttu-id="ac7f6-175">Um valor 0 que indica a hora é representado no UTC.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-175">A value of 0 that indicates the time is represented in UTC.</span></span>|  
  
     <span data-ttu-id="ac7f6-176">Os formatos para todos os dados de hora e data/hora podem incluir um elemento de fuso horário.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-176">The formats for all time and date/time data can include a time zone element.</span></span> <span data-ttu-id="ac7f6-177">Porém, o sistema ignora o valor do fuso horário, exceto quando os dados são do tipo DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-177">However, the system ignores the time zone value except when the data is of type DT_DBTIMESTAMPOFFSET.</span></span> <span data-ttu-id="ac7f6-178">Para obter mais informações, consulte [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac7f6-178">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
     <span data-ttu-id="ac7f6-179">Nos formatos que incluem um elemento de fuso horário, não há espaço entre o elemento de hora e o de fuso horário, como mostrado no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-179">In formats that include a time zone element, there is no space between the time element and the time zone element, as shown in the following example:</span></span>  
  
     <span data-ttu-id="ac7f6-180">HH:MI:SS[+HH:MI]</span><span class="sxs-lookup"><span data-stu-id="ac7f6-180">HH:MI:SS[+HH:MI]</span></span>  
  
     <span data-ttu-id="ac7f6-181">As chaves no exemplo anterior indicam que o valor do fuso horário é opcional.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-181">The brackets in the previous example indicate that the time zone value is optional.</span></span>  
  
-   <span data-ttu-id="ac7f6-182">Os formatos de hora que incluem uma fração decimal, como listados na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-182">Time formats that include a decimal fraction, as listed in the following table:</span></span>  
  
    |<span data-ttu-id="ac7f6-183">Formatar</span><span class="sxs-lookup"><span data-stu-id="ac7f6-183">Format</span></span>|<span data-ttu-id="ac7f6-184">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac7f6-184">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="ac7f6-185">HH [.nnnnnnn]</span><span class="sxs-lookup"><span data-stu-id="ac7f6-185">HH[.nnnnnnn]</span></span>|<span data-ttu-id="ac7f6-186">n é um valor entre 0 e 9999999 que representa uma fração de horas.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-186">n is a value between 0 and 9999999 that represents a fraction of hours.</span></span> <span data-ttu-id="ac7f6-187">As chaves indicam que esse valor é opcional.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-187">The brackets indicate that this value is optional.</span></span><br /><br /> <span data-ttu-id="ac7f6-188">Por exemplo, o valor 12.750 indica 12:45.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-188">For example, the value 12.750 indicates 12:45.</span></span>|  
    |<span data-ttu-id="ac7f6-189">HHMI [.nnnnnnn]</span><span class="sxs-lookup"><span data-stu-id="ac7f6-189">HHMI[.nnnnnnn]</span></span><br /><br /> <span data-ttu-id="ac7f6-190">HH:MI [.nnnnnnn]</span><span class="sxs-lookup"><span data-stu-id="ac7f6-190">HH:MI[.nnnnnnn]</span></span>|<span data-ttu-id="ac7f6-191">n é um valor entre 0 e 9999999 que representa uma fração de minutos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-191">n is a value between 0 and 9999999 that represents a fraction of minutes.</span></span> <span data-ttu-id="ac7f6-192">As chaves indicam que esse valor é opcional.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-192">The brackets indicate that this value is optional.</span></span><br /><br /> <span data-ttu-id="ac7f6-193">Por exemplo, o valor 1220.500 indica 12:20:30.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-193">For example, the value 1220.500 indicates 12:20:30.</span></span>|  
    |<span data-ttu-id="ac7f6-194">HHMISS [.nnnnnnn]</span><span class="sxs-lookup"><span data-stu-id="ac7f6-194">HHMISS[.nnnnnnn]</span></span><br /><br /> <span data-ttu-id="ac7f6-195">HH:MI:SS[.nnnnnnn]</span><span class="sxs-lookup"><span data-stu-id="ac7f6-195">HH:MI:SS[.nnnnnnn]</span></span>|<span data-ttu-id="ac7f6-196">n é um valor entre 0 e 9999999 que representa uma fração de segundos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-196">n is a value between 0 and 9999999 that represents a fraction of seconds.</span></span> <span data-ttu-id="ac7f6-197">As chaves indicam que esse valor é opcional.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-197">The brackets indicate that this value is optional.</span></span><br /><br /> <span data-ttu-id="ac7f6-198">Por exemplo, o valor 122040.250 indica 12:20:40.15.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-198">For example, the value 122040.250 indicates 12:20:40.15.</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="ac7f6-199">O separador de fração para os formatos de hora na tabela anterior pode ser um decimal ou uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-199">The fraction separator for the time formats in the previous table can be a decimal or a comma.</span></span>  
  
-   <span data-ttu-id="ac7f6-200">Os valores de hora que incluem um segundo, como mostrado nos seguintes exemplos:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-200">Time values that include a leap second, as shown in the following examples:</span></span>  
  
     <span data-ttu-id="ac7f6-201">23:59:60[.0000000]</span><span class="sxs-lookup"><span data-stu-id="ac7f6-201">23:59:60[.0000000]</span></span>  
  
     <span data-ttu-id="ac7f6-202">235960[.0000000]</span><span class="sxs-lookup"><span data-stu-id="ac7f6-202">235960[.0000000]</span></span>  
  
 <span data-ttu-id="ac7f6-203">A análise rápida efetua a saída de cadeias de caracteres como DT_DBTIME e DT_DBTIME2.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-203">Fast parse outputs the strings as DT_DBTIME and DT_DBTIME2.</span></span> <span data-ttu-id="ac7f6-204">Os valores de hora em formatos truncados são convertidos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-204">Time values in truncated formats are padded.</span></span> <span data-ttu-id="ac7f6-205">Por exemplo, HH:MI se torna HH:MM:00 .000.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-205">For example, HH:MI becomes HH:MM:00.000.</span></span>  
  
 <span data-ttu-id="ac7f6-206">Para obter mais informações, consulte [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac7f6-206">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="datetime-data-type"></a><span data-ttu-id="ac7f6-207">Tipo de dados de data/hora</span><span class="sxs-lookup"><span data-stu-id="ac7f6-207">Date/Time Data Type</span></span>  
 <span data-ttu-id="ac7f6-208">A análise rápida oferece suporte aos seguintes formatos de cadeia de caracteres para dados de data/hora:</span><span class="sxs-lookup"><span data-stu-id="ac7f6-208">Fast parse supports the following string formats for date/time data:</span></span>  
  
-   <span data-ttu-id="ac7f6-209">Formatos que incluem espaços em branco à esquerda.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-209">Formats that include leading white spaces.</span></span> <span data-ttu-id="ac7f6-210">Por exemplo, o valor "  2003-01-10T203910" é válido.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-210">For example, the value "  2003-01-10T203910" is valid.</span></span>  
  
-   <span data-ttu-id="ac7f6-211">As combinações de formatos de data e de hora válidos separados por um T maiúsculo, e os formatos de fuso horário válidos, como AAAAMMDDT[HHMISS][+HH:MI].</span><span class="sxs-lookup"><span data-stu-id="ac7f6-211">Combinations of valid date formats and valid time formats separated by an uppercase T, and valid time zone formats, such as YYYYMMDDT[HHMISS][+HH:MI].</span></span> <span data-ttu-id="ac7f6-212">Os valores de hora e de fuso horário não são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-212">The time and time zone values are not required.</span></span> <span data-ttu-id="ac7f6-213">Por exemplo, "2003-10-14" são válidos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-213">For example, "2003-10-14" is valid.</span></span>  
  
 <span data-ttu-id="ac7f6-214">A análise rápida não oferece suporte a intervalos de tempo.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-214">Fast parse does not support time intervals.</span></span> <span data-ttu-id="ac7f6-215">Por exemplo, um intervalo de tempo identificado por uma data e hora iniciais e finais no formato AAAAMMDDThhmmss/AAAAMMDDThhmmss não pode ser analisado.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-215">For example, a time interval identified by a start and end date and time in the format YYYYMMDDThhmmss/YYYYMMDDThhmmss cannot be parsed.</span></span>  
  
 <span data-ttu-id="ac7f6-216">A análise rápida efetua saídas das cadeias de caracteres como DT_DATE, DT_DBTIMESTAMP, DT_DBTIMESTAMP2 e DT_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-216">Fast parse outputs the strings as DT_DATE, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET.</span></span> <span data-ttu-id="ac7f6-217">Os valores de data/hora em formatos truncados são convertidos.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-217">Date/time values in truncated formats are padded.</span></span> <span data-ttu-id="ac7f6-218">A tabela a seguir lista os valores que são adicionados nas partes de data e hora ausentes.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-218">The following table lists the values that are added for missing date and time parts.</span></span>  
  
|<span data-ttu-id="ac7f6-219">Parte de data e hora</span><span class="sxs-lookup"><span data-stu-id="ac7f6-219">Date/Time part</span></span>|<span data-ttu-id="ac7f6-220">Preenchimento</span><span class="sxs-lookup"><span data-stu-id="ac7f6-220">Padding</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="ac7f6-221">Segundos</span><span class="sxs-lookup"><span data-stu-id="ac7f6-221">Seconds</span></span>|<span data-ttu-id="ac7f6-222">Adicione 00.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-222">Add 00.</span></span>|  
|<span data-ttu-id="ac7f6-223">minutos</span><span class="sxs-lookup"><span data-stu-id="ac7f6-223">Minutes</span></span>|<span data-ttu-id="ac7f6-224">Adicionar 00:00.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-224">Add 00:00.</span></span>|  
|<span data-ttu-id="ac7f6-225">Hora</span><span class="sxs-lookup"><span data-stu-id="ac7f6-225">Hour</span></span>|<span data-ttu-id="ac7f6-226">Adicione 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-226">Add 00:00:00.</span></span>|  
|<span data-ttu-id="ac7f6-227">Dia</span><span class="sxs-lookup"><span data-stu-id="ac7f6-227">Day</span></span>|<span data-ttu-id="ac7f6-228">Adicione 01 para o dia do mês.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-228">Add 01 for the day of the month.</span></span>|  
|<span data-ttu-id="ac7f6-229">Month</span><span class="sxs-lookup"><span data-stu-id="ac7f6-229">Month</span></span>|<span data-ttu-id="ac7f6-230">Adicione 01 para o mês do ano.</span><span class="sxs-lookup"><span data-stu-id="ac7f6-230">Add 01 for the month of the year.</span></span>|  
  
 <span data-ttu-id="ac7f6-231">Para obter mais informações, consulte [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac7f6-231">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
  