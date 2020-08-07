---
title: IDIOMA e FORMAT_STRING em FORMATED_VALUE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7534ff5f-954e-47d4-a2ed-4b5b8ccb30e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: ba4aacbbd440da6048680054771c86c40ef96daa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568815"
---
# <a name="language-and-format_string-on-formated_value"></a><span data-ttu-id="7a344-102">LANGUAGE e FORMAT_STRING em FORMATED_VALUE</span><span class="sxs-lookup"><span data-stu-id="7a344-102">LANGUAGE and FORMAT_STRING on FORMATED_VALUE</span></span>
  <span data-ttu-id="7a344-103">A propriedade FORMATTED_VALUE é criada com base nas interações das propriedades VALUE, FORMAT_STRING e LANGUAGE da célula.</span><span class="sxs-lookup"><span data-stu-id="7a344-103">The FORMATTED_VALUE property is built on the interactions of the VALUE, FORMAT_STRING and LANGUAGE properties of the cell.</span></span> <span data-ttu-id="7a344-104">Este tópico explica como essas propriedades interagem para criar a propriedade FORMATTED_VALUE.</span><span class="sxs-lookup"><span data-stu-id="7a344-104">This topic explains how these properties interact to build the FORMATTED_VALUE property.</span></span>  
  
## <a name="value-format_string-language-properties"></a><span data-ttu-id="7a344-105">Propriedades VALUE, FORMAT_STRING, LANGUAGE</span><span class="sxs-lookup"><span data-stu-id="7a344-105">VALUE, FORMAT_STRING, LANGUAGE properties</span></span>  
 <span data-ttu-id="7a344-106">A tabela a seguir explica o que são essas propriedades, para ajudá-lo na preparação para o uso combinado delas.</span><span class="sxs-lookup"><span data-stu-id="7a344-106">The following table explains what these properties are, to help prepare us to use them in combination.</span></span>  
  
 <span data-ttu-id="7a344-107">VALUE</span><span class="sxs-lookup"><span data-stu-id="7a344-107">VALUE</span></span>  
 <span data-ttu-id="7a344-108">O valor não formatado da célula.</span><span class="sxs-lookup"><span data-stu-id="7a344-108">The unformatted value of the cell.</span></span>  
  
 <span data-ttu-id="7a344-109">FORMAT_STRING</span><span class="sxs-lookup"><span data-stu-id="7a344-109">FORMAT_STRING</span></span>  
 <span data-ttu-id="7a344-110">O modelo de formatação a ser aplicado ao valor da célula para gerar a propriedade FORMATTED_VALUE</span><span class="sxs-lookup"><span data-stu-id="7a344-110">The formatting template to be applied to the value of the cell to generate FORMATTED_VALUE property</span></span>  
  
 <span data-ttu-id="7a344-111">LANGUAGE</span><span class="sxs-lookup"><span data-stu-id="7a344-111">LANGUAGE</span></span>  
 <span data-ttu-id="7a344-112">A especificação de localidade a ser aplicada junto com FORMAT_STRING para gerar uma versão localizada de FORMATTED_VALUE</span><span class="sxs-lookup"><span data-stu-id="7a344-112">The locale specification to be applied alongside FORMAT_STRING to generate a localized version of FORMATTED_VALUE</span></span>  
  
## <a name="formatted_value-constructed"></a><span data-ttu-id="7a344-113">FORMATTED_VALUE construída</span><span class="sxs-lookup"><span data-stu-id="7a344-113">FORMATTED_VALUE constructed</span></span>  
 <span data-ttu-id="7a344-114">A propriedade FORMATTED_VALUE é construída com o uso do valor da propriedade VALUE e a aplicação do modelo de formato especificado na propriedade FORMAT_STRING para esse valor.</span><span class="sxs-lookup"><span data-stu-id="7a344-114">The FORMATTED_VALUE property is constructed by using the value from the VALUE property and applying the format template specified in the FORMAT_STRING property to that value.</span></span> <span data-ttu-id="7a344-115">Além disso, sempre que o valor de formatação for um `named formatting literal`, a especificação da propriedade LANGUAGE modifica a saída de FORMAT_STRING para seguir o uso do idioma da formatação nomeada.</span><span class="sxs-lookup"><span data-stu-id="7a344-115">In addition, whenever the formatting value is a `named formatting literal` the LANGUAGE property specification modifies the output of FORMAT_STRING to follow the language usage for the named formatting.</span></span> <span data-ttu-id="7a344-116">Os literais de formatação nomeada são definidos de modo que possam ser localizados.</span><span class="sxs-lookup"><span data-stu-id="7a344-116">Named formatting literals are all defined in a way that can be localized.</span></span> <span data-ttu-id="7a344-117">Por exemplo, `"General Date"` é uma especificação que pode ser localizada, em oposição ao seguinte modelo `"YYYY-MM-DD hh:nn:ss",` , que declara que a data deve ser apresentada conforme o definido pelo modelo, independentemente da especificação de idioma.</span><span class="sxs-lookup"><span data-stu-id="7a344-117">For example, `"General Date"` is a specification that can be localized, as opposed to the following template `"YYYY-MM-DD hh:nn:ss",` which states that the date is to be presented as defined by the template regardless of the language specification.</span></span>  
  
 <span data-ttu-id="7a344-118">Se houver um conflito entre o modelo FORMAT_STRING e a especificação LANGUAGE, FORMAT_STRING substituirá LANGUAGE.</span><span class="sxs-lookup"><span data-stu-id="7a344-118">If there is a conflict between the FORMAT_STRING template and the LANGUAGE specification, the FORMAT_STRING template overrides the LANGUAGE specification.</span></span> <span data-ttu-id="7a344-119">Por exemplo, se FORMAT_STRING="$ #0" e LANGUAGE=1034 (Spain), e VALUE=123.456, D_VALUE="$ 123" em vez de FORMATTED_VALUE="€ 123", o formato esperado estará em Euros, porque o valor do modelo do formato substitui o idioma especificado.</span><span class="sxs-lookup"><span data-stu-id="7a344-119">For example, if FORMAT_STRING="$ #0" and LANGUAGE=1034 (Spain), and VALUE=123.456 then FORMATTED_VALUE="$ 123" instead of FORMATTED_VALUE="€ 123", the expected format is in Euros, because the value of the format template overrides the language specified.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="7a344-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7a344-120">Examples</span></span>  
 <span data-ttu-id="7a344-121">Os exemplos a seguir mostram a saída obtida quando LANGUAGE é usado junto com FORMAT_STRING.</span><span class="sxs-lookup"><span data-stu-id="7a344-121">The following examples show the output obtained when LANGUAGE is used in conjunction with FORMAT_STRING.</span></span>  
  
 <span data-ttu-id="7a344-122">O primeiro exemplo explica os valores numéricos da formatação; o segundo exemplo explica os valores de data e hora da formatação.</span><span class="sxs-lookup"><span data-stu-id="7a344-122">The first example explains formatting numerical values; the second example explains formatting date and time values.</span></span>  
  
 <span data-ttu-id="7a344-123">Para cada exemplo, o código MDX é atribuído.</span><span class="sxs-lookup"><span data-stu-id="7a344-123">For each example the Multidimensional Expressions (MDX) code is given.</span></span>  
  
 `with`  
  
 `member measures.A as 5040, FORMAT_STRING="Currency"`  
  
 `member measures.B as measures.A, LANGUAGE=1034`  
  
 `member measures.C as measures.A, LANGUAGE=1034 , FORMAT_STRING="$#,##0.00"`  
  
 `member measures.D as measures.A, FORMAT_STRING="Scientific"`  
  
 `member measures.E as measures.A, LANGUAGE=1034 , FORMAT_STRING="Scientific"`  
  
 `member measures.F as 0.5040, FORMAT_STRING="Percent"`  
  
 `member measures.G as measures.F, LANGUAGE=1034`  
  
 `member measures.H as 0, LANGUAGE=1034 , FORMAT_STRING="Yes/No"`  
  
 `member measures.I as 59, LANGUAGE=1034 , FORMAT_STRING="Yes/No"`  
  
 `member measures.J as 0, LANGUAGE=1034 , FORMAT_STRING="ON/OFF"`  
  
 `member measures.K as -312, LANGUAGE=1034 , FORMAT_STRING="ON/OFF"`  
  
 `Select {measures.A, measures.B, measures.C, measures.D, measures.E, measures.F, measures.G, measures.H, measures.I, measures.J, measures.K} on 0`  
  
 `from [Adventure Works]`  
  
 `cell properties VALUE, FORMAT_STRING, LANGUAGE, FORMATTED_VALUE`  
  
 <span data-ttu-id="7a344-124">Os resultados, transpostos, quando a consulta MDX acima estava sendo executada com o uso de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] em um servidor e cliente com a localidade 1033, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="7a344-124">The results, transposed, when the above MDX query was run using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] over a server and client with locale 1033 are as follows:</span></span>  
  
|<span data-ttu-id="7a344-125">Membro</span><span class="sxs-lookup"><span data-stu-id="7a344-125">Member</span></span>|<span data-ttu-id="7a344-126">FORMATTED_VALUE</span><span class="sxs-lookup"><span data-stu-id="7a344-126">FORMATTED_VALUE</span></span>|<span data-ttu-id="7a344-127">Explicação</span><span class="sxs-lookup"><span data-stu-id="7a344-127">Explanation</span></span>|  
|------------|----------------------|-----------------|  
|<span data-ttu-id="7a344-128">Um</span><span class="sxs-lookup"><span data-stu-id="7a344-128">A</span></span>|<span data-ttu-id="7a344-129">$5.040,00</span><span class="sxs-lookup"><span data-stu-id="7a344-129">$5,040.00</span></span>|<span data-ttu-id="7a344-130">FORMAT_STRING é definido como `Currency` e LANGUAGE é `1033`, informações herdadas do valor de localidade do sistema</span><span class="sxs-lookup"><span data-stu-id="7a344-130">FORMAT_STRING is set to `Currency` and LANGUAGE is `1033`, inherited from system locale value</span></span>|  
|<span data-ttu-id="7a344-131">B</span><span class="sxs-lookup"><span data-stu-id="7a344-131">B</span></span>|<span data-ttu-id="7a344-132">€ 5.040,00</span><span class="sxs-lookup"><span data-stu-id="7a344-132">€5.040,00</span></span>|<span data-ttu-id="7a344-133">FORMAT_STRING é definido como `Currency` (herdado de A) e LANGUAGE é definido explicitamente como `1034` (Spain), daí o sinal de Euro, o separador decimal e de milhar diferente.</span><span class="sxs-lookup"><span data-stu-id="7a344-133">FORMAT_STRING is set to `Currency` (inherited from A) and LANGUAGE is explicitly set to `1034` (Spain) hence the Euro sign, the different decimal separator and the different thousand separator.</span></span>|  
|<span data-ttu-id="7a344-134">C</span><span class="sxs-lookup"><span data-stu-id="7a344-134">C</span></span>|<span data-ttu-id="7a344-135">$ 5.040,00</span><span class="sxs-lookup"><span data-stu-id="7a344-135">$5.040,00</span></span>|<span data-ttu-id="7a344-136">FORMAT_STRING é definido como `$#,##0.00` , uma substituição para Moeda, de A, e LANGUAGE é definido explicitamente para `1034` (Spain).</span><span class="sxs-lookup"><span data-stu-id="7a344-136">FORMAT_STRING is set to `$#,##0.00` an override to Currency, from A, and LANGUAGE is explicitly set to `1034` (Spain).</span></span> <span data-ttu-id="7a344-137">Como a propriedade FORMAT_STRING define explicitamente o símbolo de moeda como $, FORMATTED_VALUE é apresentado com o sinal $.</span><span class="sxs-lookup"><span data-stu-id="7a344-137">Because the FORMAT_STRING property explicitly set the currency symbol to $, the FORMATTED_VALUE is presented with the $ sign.</span></span> <span data-ttu-id="7a344-138">No entanto, como `.` (ponto) e `,` (vírgula) são espaços reservados para separadores de decimal e de milhar, a especificação de idioma os afeta gerando uma saída localizada para separadores decimal e de milhar.</span><span class="sxs-lookup"><span data-stu-id="7a344-138">However, because `.` (dot) and `,` (comma) are placeholders for decimal separator and thousand separator respectively, the language specification affects them generating an output that is localized for decimal and thousand separators.</span></span>|  
|<span data-ttu-id="7a344-139">D</span><span class="sxs-lookup"><span data-stu-id="7a344-139">D</span></span>|<span data-ttu-id="7a344-140">5.04E+03</span><span class="sxs-lookup"><span data-stu-id="7a344-140">5.04E+03</span></span>|<span data-ttu-id="7a344-141">FORMAT_STRING é definido como `Scientific` e LANGUAGE é definido como `1033`, herdados do valor de localidade do sistema, por isso o `.` (ponto) é o separador decimal.</span><span class="sxs-lookup"><span data-stu-id="7a344-141">FORMAT_STRING is set to `Scientific` and LANGUAGE is set to `1033`, inherited from system locale value, hence `.` (dot) is the decimal separator.</span></span>|  
|<span data-ttu-id="7a344-142">E</span><span class="sxs-lookup"><span data-stu-id="7a344-142">E</span></span>|<span data-ttu-id="7a344-143">5,04E+03</span><span class="sxs-lookup"><span data-stu-id="7a344-143">5,04E+03</span></span>|<span data-ttu-id="7a344-144">FORMAT_STRING é definido como `Scientific` e LANGUAGE é definido explicitamente como `1034,` , por isso a `,` (vírgula) é o separador decimal.</span><span class="sxs-lookup"><span data-stu-id="7a344-144">FORMAT_STRING is set to `Scientific` and LANGUAGE is set explicitly to `1034,` hence `,` (comma) is the decimal separator.</span></span>|  
|<span data-ttu-id="7a344-145">F</span><span class="sxs-lookup"><span data-stu-id="7a344-145">F</span></span>|<span data-ttu-id="7a344-146">50,40%</span><span class="sxs-lookup"><span data-stu-id="7a344-146">50.40%</span></span>|<span data-ttu-id="7a344-147">FORMAT_STRING é definido como `Percent` e LANGUAGE é definido como `1033`, herdados do valor de localidade do sistema, por isso o `.` (ponto) é o separador decimal.</span><span class="sxs-lookup"><span data-stu-id="7a344-147">FORMAT_STRING is set to `Percent` and LANGUAGE is set to `1033`, inherited from system locale value, hence `.` (dot) is the decimal separator.</span></span><br /><br /> <span data-ttu-id="7a344-148">Observe que VALUE foi alterado de 5040 para 0.5040</span><span class="sxs-lookup"><span data-stu-id="7a344-148">Note that VALUE was changed from 5040 to 0.5040</span></span>|  
|<span data-ttu-id="7a344-149">G</span><span class="sxs-lookup"><span data-stu-id="7a344-149">G</span></span>|<span data-ttu-id="7a344-150">50,40%</span><span class="sxs-lookup"><span data-stu-id="7a344-150">50,40%</span></span>|<span data-ttu-id="7a344-151">FORMAT_STRING é definido como `Percent`, herdado de F, e LANGUAGE é definido explicitamente como `1034` , por isso a `,` (vírgula) é o separador decimal.</span><span class="sxs-lookup"><span data-stu-id="7a344-151">FORMAT_STRING is set to `Percent`, inherited from F, and LANGUAGE is set explicitly to `1034` hence `,` (comma) is the decimal separator.</span></span><br /><br /> <span data-ttu-id="7a344-152">Observe que VALUE foi herdado do valor F.</span><span class="sxs-lookup"><span data-stu-id="7a344-152">Note that VALUE was inherited from F value.</span></span>|  
|<span data-ttu-id="7a344-153">H</span><span class="sxs-lookup"><span data-stu-id="7a344-153">H</span></span>|<span data-ttu-id="7a344-154">Não</span><span class="sxs-lookup"><span data-stu-id="7a344-154">No</span></span>|<span data-ttu-id="7a344-155">FORMAT_STRING é definido como `YES/NO`, VALUE é definido como 0 e LANGUAGE é definido explicitamente como `1034`; como não há nenhuma diferença entre English NO e Spanish NO, o usuário não vê diferença em FORMATTED_VALUE.</span><span class="sxs-lookup"><span data-stu-id="7a344-155">FORMAT_STRING is set to `YES/NO`, VALUE is set to 0 and LANGUAGE is set explicitly to `1034`; because there is no difference between English NO and Spanish NO the user sees no difference in the FORMATTED_VALUE.</span></span>|  
|<span data-ttu-id="7a344-156">I</span><span class="sxs-lookup"><span data-stu-id="7a344-156">I</span></span>|<span data-ttu-id="7a344-157">SI</span><span class="sxs-lookup"><span data-stu-id="7a344-157">SI</span></span>|<span data-ttu-id="7a344-158">FORMAT_STRING é definido como `YES/NO`, VALUE é definido como 59 e LANGUAGE é definido explicitamente como `1034`; conforme definido para a formatação YES/NO, qualquer valor diferente de zero (0) é um YES e como o idioma é definido como Spanish, FORMATTED_VALUE é SI.</span><span class="sxs-lookup"><span data-stu-id="7a344-158">FORMAT_STRING is set to `YES/NO`, VALUE is set to 59 and LANGUAGE is set explicitly to `1034`; as defined for YES/NO formatting, any value different from zero (0) is a YES and because language is set to Spanish then the FORMATTED_VALUE is SI.</span></span>|  
|<span data-ttu-id="7a344-159">J</span><span class="sxs-lookup"><span data-stu-id="7a344-159">J</span></span>|<span data-ttu-id="7a344-160">Desativado</span><span class="sxs-lookup"><span data-stu-id="7a344-160">Desactivado</span></span>|<span data-ttu-id="7a344-161">FORMAT_STRING é definido como `ON/OFF`, VALUE é definido como 0 e LANGUAGE é definido explicitamente como `1034`; conforme definido para a formatação ON/OFF, qualquer valor equivalente a zero (0) é um OFF e, como o idioma está definido para Spanish, FORMATTED_VALUE é Desativado.</span><span class="sxs-lookup"><span data-stu-id="7a344-161">FORMAT_STRING is set to `ON/OFF`, VALUE is set to 0 and LANGUAGE is set explicitly to `1034`; as defined for ON/OFF formatting, any value equal to zero (0) is an OFF and because language is set to Spanish then the FORMATTED_VALUE is Desactivado.</span></span>|  
|<span data-ttu-id="7a344-162">K</span><span class="sxs-lookup"><span data-stu-id="7a344-162">K</span></span>|<span data-ttu-id="7a344-163">Ativado</span><span class="sxs-lookup"><span data-stu-id="7a344-163">Activado</span></span>|<span data-ttu-id="7a344-164">FORMAT_STRING é definido como `ON/OFF`, VALUE é definido como -312 e LANGUAGE é definido explicitamente como `1034`; conforme definido para a formatação ON/OFF, qualquer valor diferente de zero (0) é um ON e como o idioma é definido como Spanish, FORMATTED_VALUE é Ativado.</span><span class="sxs-lookup"><span data-stu-id="7a344-164">FORMAT_STRING is set to `ON/OFF`, VALUE is set to -312 and LANGUAGE is set explicitly to `1034`; as defined for ON/OFF formatting, any value different from zero (0) is an ON and because language is set to Spanish then the FORMATTED_VALUE is Activado.</span></span>|  
  
 `with`  
  
 `member measures.A as 'CDate("1959-03-12 06:30")'`  
  
 `member measures.B as measures.A, FORMAT_STRING="Long Date"`  
  
 `member measures.C as measures.A, LANGUAGE=1034 , FORMAT_STRING="General Date"`  
  
 `member measures.D as measures.A, LANGUAGE=1034, FORMAT_STRING="Long Date"`  
  
 `member measures.E as measures.A, LANGUAGE=1041 , FORMAT_STRING="General Date"`  
  
 `member measures.F as measures.A, LANGUAGE=1041 , FORMAT_STRING="Long Date"`  
  
 `member measures.G as measures.A, FORMAT_STRING="Long Time"`  
  
 `member measures.H as measures.A, FORMAT_STRING="Short Time"`  
  
 `member measures.I as measures.A, LANGUAGE=1034 , FORMAT_STRING="Long Time"`  
  
 `member measures.J as measures.A, LANGUAGE=1034 , FORMAT_STRING="Short Time"`  
  
 `member measures.K as measures.A, LANGUAGE=1041 , FORMAT_STRING="Long Time"`  
  
 `member measures.L as measures.A, LANGUAGE=1041 , FORMAT_STRING="Short Time"`  
  
 `Select {measures.A, measures.B, measures.C, measures.D, measures.E, measures.F`  
  
 `, measures.G, measures.H, measures.I, measures.J, measures.K, measures.L} on 0`  
  
 `from [Adventure Works]`  
  
 `cell properties VALUE, FORMAT_STRING, LANGUAGE, FORMATTED_VALUE`  
  
 <span data-ttu-id="7a344-165">Os resultados, transpostos, quando a consulta MDX acima estava sendo executada com o uso de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] em um servidor e cliente com a localidade 1033, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="7a344-165">The results, transposed, when the above MDX query was run using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] over a server and client with locale 1033 are as follows:</span></span>  
  
|<span data-ttu-id="7a344-166">Membro</span><span class="sxs-lookup"><span data-stu-id="7a344-166">Member</span></span>|<span data-ttu-id="7a344-167">FORMATTED_VALUE</span><span class="sxs-lookup"><span data-stu-id="7a344-167">FORMATTED_VALUE</span></span>|<span data-ttu-id="7a344-168">Explicação</span><span class="sxs-lookup"><span data-stu-id="7a344-168">Explanation</span></span>|  
|------------|----------------------|-----------------|  
|<span data-ttu-id="7a344-169">Um</span><span class="sxs-lookup"><span data-stu-id="7a344-169">A</span></span>|<span data-ttu-id="7a344-170">3/12/1959 6:30:00 AM</span><span class="sxs-lookup"><span data-stu-id="7a344-170">3/12/1959 6:30:00 AM</span></span>|<span data-ttu-id="7a344-171">FORMAT_STRING é definido implicitamente como `General Date` pela expressão CDate() e LANGUAGE é definido como `1033` (English), herdado do valor de localidade do sistema</span><span class="sxs-lookup"><span data-stu-id="7a344-171">FORMAT_STRING is set implicitly to `General Date` by the CDate() expression and LANGUAGE is `1033` (English), inherited from system locale value</span></span>|  
|<span data-ttu-id="7a344-172">B</span><span class="sxs-lookup"><span data-stu-id="7a344-172">B</span></span>|<span data-ttu-id="7a344-173">Quinta-feira, 12 de março de 1959</span><span class="sxs-lookup"><span data-stu-id="7a344-173">Thursday, March 12, 1959</span></span>|<span data-ttu-id="7a344-174">FORMAT_STRING é definido explicitamente como `Long Date` e LANGUAGE é `1033` (English), herdado do valor de localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="7a344-174">FORMAT_STRING is set explicitly to `Long Date` and LANGUAGE is `1033` (English), inherited from system locale value</span></span>|  
|<span data-ttu-id="7a344-175">C</span><span class="sxs-lookup"><span data-stu-id="7a344-175">C</span></span>|<span data-ttu-id="7a344-176">12/03/1959 6:30:00</span><span class="sxs-lookup"><span data-stu-id="7a344-176">12/03/1959 6:30:00</span></span>|<span data-ttu-id="7a344-177">FORMAT_STRING é definido explicitamente para `General Date` e LANGUAGE é explicitamente `1034` (Spanish).</span><span class="sxs-lookup"><span data-stu-id="7a344-177">FORMAT_STRING is set explicitly to `General Date` and LANGUAGE is explicitly `1034` (Spanish).</span></span><br /><br /> <span data-ttu-id="7a344-178">Observe que o mês e o dia são alternados quando comparados com o estilo de formatação dos EUA</span><span class="sxs-lookup"><span data-stu-id="7a344-178">Note that month and day are switched when compared to U.S. formatting style</span></span>|  
|<span data-ttu-id="7a344-179">D</span><span class="sxs-lookup"><span data-stu-id="7a344-179">D</span></span>|<span data-ttu-id="7a344-180">jueves, 12 de marzo de 1959</span><span class="sxs-lookup"><span data-stu-id="7a344-180">jueves, 12 de marzo de 1959</span></span>|<span data-ttu-id="7a344-181">FORMAT_STRING é definido explicitamente para `Long Date` e LANGUAGE é explicitamente `1034` (Spanish).</span><span class="sxs-lookup"><span data-stu-id="7a344-181">FORMAT_STRING is set explicitly to `Long Date` and LANGUAGE is explicitly `1034` (Spanish).</span></span><br /><br /> <span data-ttu-id="7a344-182">Observe que o mês e o dia da semana estão em espanhol</span><span class="sxs-lookup"><span data-stu-id="7a344-182">Note that month and day of the week are worded in Spanish</span></span>|  
|<span data-ttu-id="7a344-183">E</span><span class="sxs-lookup"><span data-stu-id="7a344-183">E</span></span>|<span data-ttu-id="7a344-184">1959/03/12 6:30:00</span><span class="sxs-lookup"><span data-stu-id="7a344-184">1959/03/12 6:30:00</span></span>|<span data-ttu-id="7a344-185">FORMAT_STRING é definido explicitamente para `General Date` e LANGUAGE é explicitamente `1041` (japonês).</span><span class="sxs-lookup"><span data-stu-id="7a344-185">FORMAT_STRING is set explicitly to `General Date` and LANGUAGE is explicitly `1041` (Japanese).</span></span><br /><br /> <span data-ttu-id="7a344-186">Observe que a data agora está formatada como Ano/Mês/Dia Hora:Minutos:Segundos</span><span class="sxs-lookup"><span data-stu-id="7a344-186">Note that the date is now formatted Year/Month/Day Hour:Minutes:Seconds</span></span>|  
|<span data-ttu-id="7a344-187">F</span><span class="sxs-lookup"><span data-stu-id="7a344-187">F</span></span>|<span data-ttu-id="7a344-188">1959 年 3 月 12 日</span><span class="sxs-lookup"><span data-stu-id="7a344-188">1959年3月12日</span></span>|<span data-ttu-id="7a344-189">FORMAT_STRING é definido explicitamente para `Long Date` e LANGUAGE é explicitamente `1041` (japonês).</span><span class="sxs-lookup"><span data-stu-id="7a344-189">FORMAT_STRING is set explicitly to `Long Date` and LANGUAGE is explicitly `1041` (Japanese).</span></span>|  
|<span data-ttu-id="7a344-190">G</span><span class="sxs-lookup"><span data-stu-id="7a344-190">G</span></span>|<span data-ttu-id="7a344-191">6:30:00 AM</span><span class="sxs-lookup"><span data-stu-id="7a344-191">6:30:00 AM</span></span>|<span data-ttu-id="7a344-192">FORMAT_STRING é definido explicitamente como `Long Time` e LANGUAGE é `1033` (English), herdado do valor de localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="7a344-192">FORMAT_STRING is set explicitly to `Long Time` and LANGUAGE is `1033` (English), inherited from system locale value.</span></span>|  
|<span data-ttu-id="7a344-193">H</span><span class="sxs-lookup"><span data-stu-id="7a344-193">H</span></span>|<span data-ttu-id="7a344-194">06:30</span><span class="sxs-lookup"><span data-stu-id="7a344-194">06:30</span></span>|<span data-ttu-id="7a344-195">FORMAT_STRING é definido explicitamente como `Short Time` e LANGUAGE é `1033` (English), herdado do valor de localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="7a344-195">FORMAT_STRING is set explicitly to `Short Time` and LANGUAGE is `1033` (English), inherited from system locale value.</span></span>|  
|<span data-ttu-id="7a344-196">I</span><span class="sxs-lookup"><span data-stu-id="7a344-196">I</span></span>|<span data-ttu-id="7a344-197">6:30:00</span><span class="sxs-lookup"><span data-stu-id="7a344-197">6:30:00</span></span>|<span data-ttu-id="7a344-198">FORMAT_STRING é definido explicitamente para `Long Time` e LANGUAGE é definido explicitamente como `1034` (Spanish).</span><span class="sxs-lookup"><span data-stu-id="7a344-198">FORMAT_STRING is set explicitly to `Long Time` and LANGUAGE is set explicitly to `1034` (Spanish).</span></span>|  
|<span data-ttu-id="7a344-199">J</span><span class="sxs-lookup"><span data-stu-id="7a344-199">J</span></span>|<span data-ttu-id="7a344-200">06:30</span><span class="sxs-lookup"><span data-stu-id="7a344-200">06:30</span></span>|<span data-ttu-id="7a344-201">FORMAT_STRING é definido explicitamente para `Short Time` e LANGUAGE é definido explicitamente como `1034` (Spanish).</span><span class="sxs-lookup"><span data-stu-id="7a344-201">FORMAT_STRING is set explicitly to `Short Time` and LANGUAGE is set explicitly to `1034` (Spanish).</span></span>|  
|<span data-ttu-id="7a344-202">K</span><span class="sxs-lookup"><span data-stu-id="7a344-202">K</span></span>|<span data-ttu-id="7a344-203">6:30:00</span><span class="sxs-lookup"><span data-stu-id="7a344-203">6:30:00</span></span>|<span data-ttu-id="7a344-204">FORMAT_STRING é definido explicitamente para `Long Time` e LANGUAGE é explicitamente `1041` (Japanese).</span><span class="sxs-lookup"><span data-stu-id="7a344-204">FORMAT_STRING is set explicitly to `Long Time` and LANGUAGE is set explicitly to `1041` (Japanese).</span></span>|  
|<span data-ttu-id="7a344-205">L</span><span class="sxs-lookup"><span data-stu-id="7a344-205">L</span></span>|<span data-ttu-id="7a344-206">06:30</span><span class="sxs-lookup"><span data-stu-id="7a344-206">06:30</span></span>|<span data-ttu-id="7a344-207">FORMAT_STRING é definido explicitamente para `Short Time` e LANGUAGE é explicitamente `1041` (Japanese).</span><span class="sxs-lookup"><span data-stu-id="7a344-207">FORMAT_STRING is set explicitly to `Short Time` and LANGUAGE is set explicitly to `1041` (Japanese).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a344-208">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7a344-208">See Also</span></span>  
 <span data-ttu-id="7a344-209">[FORMAT_STRING conteúdo &#40;MDX&#41;](mdx-cell-properties-format-string-contents.md) </span><span class="sxs-lookup"><span data-stu-id="7a344-209">[FORMAT_STRING Contents &#40;MDX&#41;](mdx-cell-properties-format-string-contents.md) </span></span>  
 <span data-ttu-id="7a344-210">[Usando propriedades de célula &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7a344-210">[Using Cell Properties &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md) </span></span>  
 <span data-ttu-id="7a344-211">[Criando e usando valores de propriedade &#40;MDX&#41;](../../creating-and-using-property-values-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="7a344-211">[Creating and Using Property Values &#40;MDX&#41;](../../creating-and-using-property-values-mdx.md) </span></span>  
 [<span data-ttu-id="7a344-212">Conceitos básicos de consulta MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a344-212">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
