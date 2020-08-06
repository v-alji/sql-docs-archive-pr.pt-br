---
title: HEX (expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- hexadecimal data
- HEX function
ms.assetid: f5d471ee-aeef-421c-b6e1-55b9676c3842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 640ae38ec5d2cd5ffb448e9aebde5ba5ceba2684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683631"
---
# <a name="hex-ssis-expression"></a><span data-ttu-id="83eca-102">HEX (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="83eca-102">HEX (SSIS Expression)</span></span>
  <span data-ttu-id="83eca-103">Retorna uma cadeia de caracteres que representa o valor hexadecimal de um inteiro.</span><span class="sxs-lookup"><span data-stu-id="83eca-103">Returns a string representing the hexadecimal value of an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83eca-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="83eca-104">Syntax</span></span>  
  
```  
  
HEX(integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="83eca-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="83eca-105">Arguments</span></span>  
 <span data-ttu-id="83eca-106">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="83eca-106">*integer_expression*</span></span>  
 <span data-ttu-id="83eca-107">É um inteiro assinado ou não assinado.</span><span class="sxs-lookup"><span data-stu-id="83eca-107">Is a signed or unsigned integer.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="83eca-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="83eca-108">Result Types</span></span>  
 <span data-ttu-id="83eca-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="83eca-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83eca-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="83eca-110">Remarks</span></span>  
 <span data-ttu-id="83eca-111">HEX retornará nulo se *integer_expression* for nulo.</span><span class="sxs-lookup"><span data-stu-id="83eca-111">HEX returns null if *integer_expression* is null.</span></span>  
  
 <span data-ttu-id="83eca-112">O argumento *integer_expression* deve ser avaliado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="83eca-112">The *integer_expression* argument must evaluate to an integer.</span></span> <span data-ttu-id="83eca-113">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="83eca-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="83eca-114">O resultado de retorno não inclui qualificadores como o prefixo 0x.</span><span class="sxs-lookup"><span data-stu-id="83eca-114">The return result does not include qualifiers such as the 0x prefix.</span></span> <span data-ttu-id="83eca-115">Para incluir um prefixo, use o operador + (Concatenar).</span><span class="sxs-lookup"><span data-stu-id="83eca-115">To include a prefix, use the + (Concatenate) operator.</span></span> <span data-ttu-id="83eca-116">Para obter mais informações, consulte [+ &#40;Concatenar&#41; &#40;Expressão SSIS&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="83eca-116">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="83eca-117">As letras A – F, usadas em notações HEX, são exibidas em letras maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="83eca-117">The letters A - F, used in HEX notations, appear as uppercase characters.</span></span>  
  
 <span data-ttu-id="83eca-118">O tamanho da cadeia de caracteres resultante para tipos de dados inteiro é:</span><span class="sxs-lookup"><span data-stu-id="83eca-118">The length of the resulting string for integer data types is as follows:</span></span>  
  
-   <span data-ttu-id="83eca-119">DT_I1 e DT_UI1 retornam uma cadeia de caracteres com um comprimento máximo de 2.</span><span class="sxs-lookup"><span data-stu-id="83eca-119">DT_I1 and DT_UI1 return a string with a maximum length of 2.</span></span>  
  
-   <span data-ttu-id="83eca-120">DT_I2 e DT_UI2 retornam uma cadeia de caracteres com um comprimento máximo de 4.</span><span class="sxs-lookup"><span data-stu-id="83eca-120">DT_I2 and DT_UI2 return a string with a maximum length of 4.</span></span>  
  
-   <span data-ttu-id="83eca-121">DT_I4 e DT_UI4 retornam uma cadeia de caracteres com um comprimento máximo de 8.</span><span class="sxs-lookup"><span data-stu-id="83eca-121">DT_I4 and DT_UI4 return a string with a maximum length of 8.</span></span>  
  
-   <span data-ttu-id="83eca-122">DT_I8 e DT_UI8 retornam uma cadeia de caracteres com um comprimento máximo de 16.</span><span class="sxs-lookup"><span data-stu-id="83eca-122">DT_I8 and DT_UI8 return a string with a maximum length of 16.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="83eca-123">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="83eca-123">Expression Examples</span></span>  
 <span data-ttu-id="83eca-124">Esse exemplo usa um literal numérico.</span><span class="sxs-lookup"><span data-stu-id="83eca-124">This example uses a numeric literal.</span></span> <span data-ttu-id="83eca-125">A função retorna o valor 190.</span><span class="sxs-lookup"><span data-stu-id="83eca-125">The function returns the value 190.</span></span>  
  
```  
HEX(400)   
```  
  
 <span data-ttu-id="83eca-126">Esse exemplo usa a coluna **ReorderPoint** .</span><span class="sxs-lookup"><span data-stu-id="83eca-126">This example uses the **ReorderPoint** column.</span></span> <span data-ttu-id="83eca-127">O tipo de dados da coluna é `smallint`.</span><span class="sxs-lookup"><span data-stu-id="83eca-127">The column data type is `smallint`.</span></span> <span data-ttu-id="83eca-128">Se **ReorderPoint** for 750, a função retornará 2EE.</span><span class="sxs-lookup"><span data-stu-id="83eca-128">If **ReorderPoint** is 750, the function returns 2EE.</span></span>  
  
```  
HEX(ReorderPoint)   
```  
  
 <span data-ttu-id="83eca-129">Esse exemplo usa **LocaleID**, uma variável de sistema.</span><span class="sxs-lookup"><span data-stu-id="83eca-129">This example uses **LocaleID**, a system variable.</span></span> <span data-ttu-id="83eca-130">Se **LocaleID** for 1033, a função retornará 409.</span><span class="sxs-lookup"><span data-stu-id="83eca-130">If **LocaleID** is 1033, the function returns 409.</span></span>  
  
```  
HEX(@LocaleID)  
```  
  
## <a name="see-also"></a><span data-ttu-id="83eca-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83eca-131">See Also</span></span>  
 [<span data-ttu-id="83eca-132">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="83eca-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
