---
title: Cast (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CAST function
- cast operator
- converting data types [Integration Services]
- data types [Integration Services], expressions
- data types [Integration Services], converting
ms.assetid: d4e915cc-1c7b-4b2e-93b0-13a8b0cb9242
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65d60eca4340b65b8a82855c3f2b29a6cda56e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683642"
---
# <a name="cast-ssis-expression"></a><span data-ttu-id="ca5b3-102">Cast (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca5b3-102">Cast (SSIS Expression)</span></span>
  <span data-ttu-id="ca5b3-103">Converte explicitamente uma expressão de um tipo de dados em um tipo de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-103">Explicitly converts an expression from one data type to a different data type.</span></span> <span data-ttu-id="ca5b3-104">O operador cast também pode funcionar como um operador de truncamento.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-104">The cast operator can also function as a truncation operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca5b3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ca5b3-105">Syntax</span></span>

```

(type_spec) expression

```

## <a name="arguments"></a><span data-ttu-id="ca5b3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ca5b3-106">Arguments</span></span>
 <span data-ttu-id="ca5b3-107">*type_spec* É um [!INCLUDE[ssIS](../../includes/ssis-md.md)] tipo de dados válido.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-107">*type_spec* Is a valid [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span>

 <span data-ttu-id="ca5b3-108">*expressão* de É uma expressão válida.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-108">*expression* Is a valid expression.</span></span>

## <a name="result-types"></a><span data-ttu-id="ca5b3-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="ca5b3-109">Result Types</span></span>
 <span data-ttu-id="ca5b3-110">O tipo de dados de *type_spec*.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-110">The data type of *type_spec*.</span></span> <span data-ttu-id="ca5b3-111">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca5b3-111">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="ca5b3-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="ca5b3-112">Remarks</span></span>
 <span data-ttu-id="ca5b3-113">O diagrama a seguir mostra operações de conversão legais.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-113">The following diagram shows legal cast operations.</span></span>

 <span data-ttu-id="ca5b3-114">![Conversões válidas e não válidas entre tipos de dados](../media/data-conversion.gif "Conversões válidas e não válidas entre tipos de dados")</span><span class="sxs-lookup"><span data-stu-id="ca5b3-114">![Legal and not legal casts between data types](../media/data-conversion.gif "Legal and not legal casts between data types")</span></span>

 <span data-ttu-id="ca5b3-115">A conversão para alguns tipos de dados requer parâmetros.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-115">Casting to some data types requires parameters.</span></span> <span data-ttu-id="ca5b3-116">A tabela a seguir lista esses tipos de dados e seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-116">The following table lists these data types and their parameters.</span></span>

|<span data-ttu-id="ca5b3-117">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ca5b3-117">Data type</span></span>|<span data-ttu-id="ca5b3-118">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="ca5b3-118">Parameter</span></span>|<span data-ttu-id="ca5b3-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ca5b3-119">Example</span></span>|
|---------------|---------------|-------------|
|<span data-ttu-id="ca5b3-120">DT_STR</span><span class="sxs-lookup"><span data-stu-id="ca5b3-120">DT_STR</span></span>|<span data-ttu-id="ca5b3-121">*charCount*</span><span class="sxs-lookup"><span data-stu-id="ca5b3-121">*charcount*</span></span><br /><br /> <span data-ttu-id="ca5b3-122">*código*</span><span class="sxs-lookup"><span data-stu-id="ca5b3-122">*codepage*</span></span>|<span data-ttu-id="ca5b3-123">(DT_STR,30,1252) converte 30 bytes ou 30 caracteres únicos, para o tipo de dados DT_STR usando a página de código 1252.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-123">(DT_STR,30,1252) casts 30 bytes, or 30 single characters, to the DT_STR data type using the 1252 code page.</span></span>|
|<span data-ttu-id="ca5b3-124">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="ca5b3-124">DT_WSTR</span></span>|<span data-ttu-id="ca5b3-125">*CharCount*</span><span class="sxs-lookup"><span data-stu-id="ca5b3-125">*Charcount*</span></span>|<span data-ttu-id="ca5b3-126">(DT_WSTR,20) converte 20 pares de bytes, ou 20 caracteres Unicode, para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-126">(DT_WSTR,20) casts 20 byte pairs, or 20 Unicode characters, to the DT_WSTR data type.</span></span>|
|<span data-ttu-id="ca5b3-127">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="ca5b3-127">DT_BYTES</span></span>|<span data-ttu-id="ca5b3-128">*ByteCount*</span><span class="sxs-lookup"><span data-stu-id="ca5b3-128">*Bytecount*</span></span>|<span data-ttu-id="ca5b3-129">(DT_BYTES,50) converte 50 bytes para o tipo de dados de DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-129">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|
|<span data-ttu-id="ca5b3-130">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="ca5b3-130">DT_DECIMAL</span></span>|<span data-ttu-id="ca5b3-131">*Escala*</span><span class="sxs-lookup"><span data-stu-id="ca5b3-131">*Scale*</span></span>|<span data-ttu-id="ca5b3-132">(DT_DECIMAL,2) converte um valor numérico para o tipo de dados DT_DECIMAL usando uma escala de 2.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-132">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|
|<span data-ttu-id="ca5b3-133">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="ca5b3-133">DT_NUMERIC</span></span>|<span data-ttu-id="ca5b3-134">*Precisão*</span><span class="sxs-lookup"><span data-stu-id="ca5b3-134">*Precision*</span></span><br /><br /> <span data-ttu-id="ca5b3-135">*Escala*</span><span class="sxs-lookup"><span data-stu-id="ca5b3-135">*Scale*</span></span>|<span data-ttu-id="ca5b3-136">(DT_NUMERIC,10,3) converte um valor numérico para o tipo de dados DT_NUMERIC usando uma precisão de 10 e uma escala de 3.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-136">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|
|<span data-ttu-id="ca5b3-137">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="ca5b3-137">DT_TEXT</span></span>|<span data-ttu-id="ca5b3-138">*Código*</span><span class="sxs-lookup"><span data-stu-id="ca5b3-138">*Codepage*</span></span>|<span data-ttu-id="ca5b3-139">(DT_TEXT,1252) converte um valor para o tipo de dados DT_TEXT usando a página de código 1252.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-139">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|

 <span data-ttu-id="ca5b3-140">Quando uma cadeia de caracteres é convertida para um DT_DATE, ou vice-versa, a localidade da transformação é usada.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-140">When a string is cast to a DT_DATE, or vice versa, the locale of the transformation is used.</span></span> <span data-ttu-id="ca5b3-141">Entretanto, a data está no formato ISO de AAAA-MM-DD, independentemente da preferência de localidade usada no formato ISO.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-141">However, the date is in the ISO format of YYYY-MM-DD, regardless of whether the locale preference uses the ISO format.</span></span>

> [!NOTE]
>  <span data-ttu-id="ca5b3-142">Para converter uma cadeia de caracteres para um tipo de dados de data diferente de DT_DATE, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca5b3-142">To convert a string to a date data type other than DT_DATE, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="ca5b3-143">Se a página de código for uma página de código de caractere de multibyte, o número de bytes e caracteres poderá diferir.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-143">If the code page is a multibyte character code page, the number of bytes and characters may differ.</span></span> <span data-ttu-id="ca5b3-144">A conversão de DT_WSTR para DT_STR com o mesmo valor de *charcount* pode causar truncamento dos caracteres finais na cadeia de caracteres convertidos.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-144">Casting from a DT_WSTR to a DT_STR with the same *charcount* value may cause truncation of the final characters in the converted string.</span></span> <span data-ttu-id="ca5b3-145">Se armazenamento suficiente estiver disponível na coluna da tabela de destino, defina o valor do parâmetro *charcount* para refletir o número de bytes que a página de código de multibyte exige.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-145">If sufficient storage is available in the column of the destination table, set the value of the *charcount* parameter to reflect the number of bytes that the multibyte code page requires.</span></span> <span data-ttu-id="ca5b3-146">Por exemplo, se você converter dados de caractere para um tipo de dados DT_STR usando a página de código 936, deverá definir *charcount* para um valor até duas vezes maior que o número de caracteres que você espera que os dados contenham; se você converter os dados de caracteres usando a página de código UTF-8, deverá definir *charcount* para um valor até quatro vezes maior.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-146">For example, if you cast character data to a DT_STR data type using the 936 code page, you should set *charcount* to a value up to two times greater than the number of characters that you expect the data to contain; if you cast character data using the UTF-8 code page, you should set *charcount* to a value up to four times greater.</span></span>

 <span data-ttu-id="ca5b3-147">Para obter mais informações sobre a estrutura dos tipos de dados de data, consulte [Tipos de Dados do Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca5b3-147">For more information about the structure of date data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="ssis-expression-examples"></a><span data-ttu-id="ca5b3-148">Exemplos de expressões SSIS</span><span class="sxs-lookup"><span data-stu-id="ca5b3-148">SSIS Expression Examples</span></span>
 <span data-ttu-id="ca5b3-149">Este exemplo converte um valor numérico para um inteiro.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-149">This example casts a numeric value to an integer.</span></span>

```
(DT_I4) 3.57
```

 <span data-ttu-id="ca5b3-150">Este exemplo converte um inteiro para uma cadeia de caracteres usando a página de código 1252.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-150">This example casts an integer to a character string using the 1252 code page.</span></span>

```
(DT_STR,1,1252)5
```

 <span data-ttu-id="ca5b3-151">Este exemplo converte uma cadeia de três caracteres para caracteres de byte duplo.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-151">This example casts a three-character string to double-byte characters.</span></span>

```
(DT_WSTR,3)"Cat"
```

 <span data-ttu-id="ca5b3-152">Este exemplo converte um inteiro para um decimal com uma escala de dois.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-152">This example casts an integer to a decimal with a scale of two.</span></span>

```
(DT_DECIMAl,2)500
```

 <span data-ttu-id="ca5b3-153">Este exemplo converte um inteiro para um numérico com uma precisão de sete e escala de três.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-153">This example casts an integer to a numeric with a precision of seven and scale of three.</span></span>

```
(DT_NUMERIC,7,3)4000
```

 <span data-ttu-id="ca5b3-154">Este exemplo converte valores na coluna **FirstName** , definidos com um tipo de dados **nvarchar** e um comprimento de 50, para uma cadeia de caracteres usando a página de código 1252.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-154">This example casts values in the **FirstName** column, defined with an **nvarchar** data type and a length of 50, to a character string using the 1252 code page.</span></span>

```
(DT_STR,50,1252)FirstName
```

 <span data-ttu-id="ca5b3-155">Este exemplo converte valores na coluna **DateFirstPurchase** do tipo DT_DBDATE em uma cadeia de caracteres Unicode de comprimento 20.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-155">This example casts values in the **DateFirstPurchase** column of type DT_DBDATE, to a Unicode character string with a length of 20.</span></span>

```
(DT_WSTR,20)DateFirstPurchase
```

 <span data-ttu-id="ca5b3-156">Este exemplo converte o literal da cadeia de caracteres "True" para um Booliano.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-156">This example casts the string literal "True" to a Boolean.</span></span>

```
(DT_BOOL)"True"
```

 <span data-ttu-id="ca5b3-157">Este exemplo converte um literal de cadeia de caracteres para DT_DBDATE.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-157">This example casts a string literal to DT_DBDATE.</span></span>

```
(DT_DBDATE) "1999-10-11"
```

 <span data-ttu-id="ca5b3-158">Este exemplo converte um literal de cadeia de caracteres para o tipo de dados DT_DBTIME2 que usa 5 dígitos para segundos fracionários.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-158">This example casts a string literal to the DT_DBTIME2 data type that uses 5 digits for fractional seconds.</span></span> <span data-ttu-id="ca5b3-159">(O tipo de dados DT_DBTIME2 pode ter entre 0 e 7 dígitos especificados para segundos fracionários.)</span><span class="sxs-lookup"><span data-stu-id="ca5b3-159">(The DT_DBTIME2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIME2, 5) "16:34:52.12345"
```

 <span data-ttu-id="ca5b3-160">Este exemplo converte um literal de cadeia de caracteres para o tipo de dados DT_DBTIMESTAMP2 que usa 4 dígitos para segundos fracionários.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-160">This example casts a string literal to the DT_DBTIMESTAMP2 data type that uses 4 digits for fractional seconds.</span></span> <span data-ttu-id="ca5b3-161">(O tipo de dados DT_DBTIMESTAMP2 pode ter entre 0 e 7 dígitos especificados para segundos fracionários.)</span><span class="sxs-lookup"><span data-stu-id="ca5b3-161">(The DT_DBTIMESTAMP2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMP2, 4) "1999-10-11 16:34:52.1234"
```

 <span data-ttu-id="ca5b3-162">Este exemplo converte um literal de cadeia de caracteres para o tipo de dados DT_DBTIMESTAMPOFFSET que usa 7 dígitos para segundos fracionários.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-162">This example casts a string literal to the DT_DBTIMESTAMPOFFSET data type that uses 7 digits for fractional seconds.</span></span> <span data-ttu-id="ca5b3-163">(O tipo de dados DT_DBTIMESTAMPOFFSET pode ter entre 0 e 7 dígitos especificados para segundos fracionários.)</span><span class="sxs-lookup"><span data-stu-id="ca5b3-163">(The DT_DBTIMESTAMPOFFSET data typecan have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMPOFFSET, 7) "1999-10-11 16:34:52.1234567 + 5:35"
```

## <a name="see-also"></a><span data-ttu-id="ca5b3-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca5b3-164">See Also</span></span>
 <span data-ttu-id="ca5b3-165">[Precedência de operador e operadores de associação](operator-precedence-and-associativity.md) [&#40;expressão ssis&#41;](operators-ssis-expression.md) [Integration Services &#40;expressões&#41; SSIS](integration-services-ssis-expressions.md) [Integration Services tipos de dados em expressões](integration-services-data-types-in-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="ca5b3-165">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md)</span></span>


