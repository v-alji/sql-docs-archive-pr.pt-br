---
title: NULL (expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- NULL function
- null values [Integration Services]
ms.assetid: df144237-3fbb-41ac-8624-efd92b6522b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14cd51b4e245ca6984a4c62eae2b9d5536ab1f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569562"
---
# <a name="null-ssis-expression"></a><span data-ttu-id="c70fd-102">NULL (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="c70fd-102">NULL (SSIS Expression)</span></span>
  <span data-ttu-id="c70fd-103">Retorna um valor nulo de um tipo de dados solicitado.</span><span class="sxs-lookup"><span data-stu-id="c70fd-103">Returns a null value of a requested data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c70fd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c70fd-104">Syntax</span></span>  
  
```  
  
NULL(typespec)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c70fd-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c70fd-105">Arguments</span></span>  
 <span data-ttu-id="c70fd-106">*typespec*</span><span class="sxs-lookup"><span data-stu-id="c70fd-106">*typespec*</span></span>  
 <span data-ttu-id="c70fd-107">É um tipo de dados válido.</span><span class="sxs-lookup"><span data-stu-id="c70fd-107">Is a valid data type.</span></span> <span data-ttu-id="c70fd-108">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c70fd-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c70fd-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c70fd-109">Result Types</span></span>  
 <span data-ttu-id="c70fd-110">Qualquer tipo de dados válido com um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="c70fd-110">Any valid data type with a null value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c70fd-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="c70fd-111">Remarks</span></span>  
 <span data-ttu-id="c70fd-112">NULL retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="c70fd-112">NULL returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="c70fd-113">Os parâmetros são exigidos para solicitar um valor nulo para alguns tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="c70fd-113">Parameters are required to request a null value for some data types.</span></span> <span data-ttu-id="c70fd-114">A tabela a seguir lista esses tipos de dados e seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c70fd-114">The following table lists these data types and their parameters.</span></span>  
  
|<span data-ttu-id="c70fd-115">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c70fd-115">Data type</span></span>|<span data-ttu-id="c70fd-116">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="c70fd-116">Parameter</span></span>|<span data-ttu-id="c70fd-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c70fd-117">Example</span></span>|  
|---------------|---------------|-------------|  
|<span data-ttu-id="c70fd-118">DT_STR</span><span class="sxs-lookup"><span data-stu-id="c70fd-118">DT_STR</span></span>|<span data-ttu-id="c70fd-119">*charcount*</span><span class="sxs-lookup"><span data-stu-id="c70fd-119">*charcount*</span></span><br /><br /> <span data-ttu-id="c70fd-120">*codepage*</span><span class="sxs-lookup"><span data-stu-id="c70fd-120">*codepage*</span></span>|<span data-ttu-id="c70fd-121">(DT_STR,30,1252) converte 30 caracteres para o tipo de dados de DT_STR usando a página de código 1252.</span><span class="sxs-lookup"><span data-stu-id="c70fd-121">(DT_STR,30,1252) casts 30 characters to the DT_STR data type using the 1252 code page.</span></span>|  
|<span data-ttu-id="c70fd-122">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="c70fd-122">DT_WSTR</span></span>|<span data-ttu-id="c70fd-123">*charcount*</span><span class="sxs-lookup"><span data-stu-id="c70fd-123">*charcount*</span></span>|<span data-ttu-id="c70fd-124">(DT_WSTR,20) converte 20 caracteres para o tipo de dados de DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c70fd-124">(DT_WSTR,20) casts 20 characters to the DT_WSTR data type.</span></span>|  
|<span data-ttu-id="c70fd-125">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="c70fd-125">DT_BYTES</span></span>|<span data-ttu-id="c70fd-126">*bytecount*</span><span class="sxs-lookup"><span data-stu-id="c70fd-126">*bytecount*</span></span>|<span data-ttu-id="c70fd-127">(DT_BYTES,50) converte 50 bytes para o tipo de dados de DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="c70fd-127">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|  
|<span data-ttu-id="c70fd-128">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="c70fd-128">DT_DECIMAL</span></span>|<span data-ttu-id="c70fd-129">*scale*</span><span class="sxs-lookup"><span data-stu-id="c70fd-129">*scale*</span></span>|<span data-ttu-id="c70fd-130">(DT_DECIMAL,2) converte um valor numérico para o tipo de dados DT_DECIMAL usando uma escala de 2.</span><span class="sxs-lookup"><span data-stu-id="c70fd-130">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|  
|<span data-ttu-id="c70fd-131">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="c70fd-131">DT_NUMERIC</span></span>|<span data-ttu-id="c70fd-132">*precisão*</span><span class="sxs-lookup"><span data-stu-id="c70fd-132">*precision*</span></span><br /><br /> <span data-ttu-id="c70fd-133">*scale*</span><span class="sxs-lookup"><span data-stu-id="c70fd-133">*scale*</span></span>|<span data-ttu-id="c70fd-134">(DT_NUMERIC,10,3) converte um valor numérico para o tipo de dados DT_NUMERIC usando uma precisão de 10 e uma escala de 3.</span><span class="sxs-lookup"><span data-stu-id="c70fd-134">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|  
|<span data-ttu-id="c70fd-135">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="c70fd-135">DT_TEXT</span></span>|<span data-ttu-id="c70fd-136">*codepage*</span><span class="sxs-lookup"><span data-stu-id="c70fd-136">*codepage*</span></span>|<span data-ttu-id="c70fd-137">(DT_TEXT,1252) converte um valor para o tipo de dados DT_TEXT usando a página de código 1252.</span><span class="sxs-lookup"><span data-stu-id="c70fd-137">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="c70fd-138">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="c70fd-138">Expression Examples</span></span>  
 <span data-ttu-id="c70fd-139">Esses exemplos retornam o valor nulo dos tipos de dados: DT_STR, DT_DATE e DT_BOOL.</span><span class="sxs-lookup"><span data-stu-id="c70fd-139">These examples return the null value of the data types: DT_STR, DT_DATE, and DT_BOOL.</span></span>  
  
```  
NULL(DT_STR,10,1252)  
NULL(DT_DATE)  
NULL(DT_BOOL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c70fd-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c70fd-140">See Also</span></span>  
 <span data-ttu-id="c70fd-141">[ISNULL &#40;Expressão SSIS&#41;](null-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="c70fd-141">[ISNULL &#40;SSIS Expression&#41;](null-ssis-expression.md) </span></span>  
 [<span data-ttu-id="c70fd-142">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c70fd-142">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
