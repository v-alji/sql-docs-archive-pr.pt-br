---
title: REPLICATE (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REPLICATE function
ms.assetid: e7a37b93-6d1d-42d5-9a65-de1790abf6a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9502df5bc20c6ad85f1f98fb57fe6b3cf431cc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681024"
---
# <a name="replicate-ssis-expression"></a><span data-ttu-id="0f261-102">REPLICATE (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="0f261-102">REPLICATE (SSIS Expression)</span></span>
  <span data-ttu-id="0f261-103">Retorna uma expressão de caractere que é replicada várias vezes.</span><span class="sxs-lookup"><span data-stu-id="0f261-103">Returns a character expression that is replicated a number of times.</span></span> <span data-ttu-id="0f261-104">O argumento *times* deve ser avaliado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="0f261-104">The *times* argument must evaluate to an integer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f261-105">A função REPLICATE usa com frequência cadeias longas e, portanto, é mais provável de incorrer o limite de 4.000 caracteres no tamanho da expressão.</span><span class="sxs-lookup"><span data-stu-id="0f261-105">The REPLICATE function frequently uses long strings, and therefore is more likely to incur the 4000-character limit on expression length.</span></span> <span data-ttu-id="0f261-106">Se o resultado da avaliação de uma expressão tiver o tipo de dados DT_WSTR ou DT_STR do Integration Services, a expressão truncará em 4.000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f261-106">If the evaluation result of an expression has the Integration Services data type DT_WSTR or DT_STR, the expression will be truncated at 4000 characters.</span></span> <span data-ttu-id="0f261-107">Se o tipo de resultado de uma subexpressão for DT_STR ou DT_WSTR, essa subexpressão será truncada em 4.000 caracteres, independentemente do tipo de resultado da expressão geral.</span><span class="sxs-lookup"><span data-stu-id="0f261-107">If the result type of a sub-expression is DT_STR or DT_WSTR, that sub-expression likewise will be truncated to 4000 characters, regardless of the overall expression result type.</span></span> <span data-ttu-id="0f261-108">As consequências do truncamento podem ser controladas muito bem ou causam um aviso ou um erro.</span><span class="sxs-lookup"><span data-stu-id="0f261-108">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="0f261-109">Para obter mais informações, consulte [Sintaxe &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="0f261-109">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f261-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0f261-110">Syntax</span></span>  
  
```  
  
REPLICATE(character_expression,times)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f261-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0f261-111">Arguments</span></span>  
 <span data-ttu-id="0f261-112">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="0f261-112">*character_expression*</span></span>  
 <span data-ttu-id="0f261-113">É uma expressão de caractere a ser replicada.</span><span class="sxs-lookup"><span data-stu-id="0f261-113">Is a character expression to replicate.</span></span>  
  
 <span data-ttu-id="0f261-114">*times*</span><span class="sxs-lookup"><span data-stu-id="0f261-114">*times*</span></span>  
 <span data-ttu-id="0f261-115">É uma expressão de inteiro que especifica o número de vezes que *character_expression* é replicado.</span><span class="sxs-lookup"><span data-stu-id="0f261-115">Is an integer expression that specifies the number of times *character_expression* is replicated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0f261-116">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="0f261-116">Result Types</span></span>  
 <span data-ttu-id="0f261-117">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="0f261-117">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f261-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="0f261-118">Remarks</span></span>  
 <span data-ttu-id="0f261-119">Se *times* for zero, a função retornará uma cadeia de comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="0f261-119">If *times* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="0f261-120">Se *times* for um número negativo, a função retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="0f261-120">If *times* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="0f261-121">O argumento *times* também pode usar variáveis e colunas.</span><span class="sxs-lookup"><span data-stu-id="0f261-121">The *times* argument can also use variables and columns.</span></span>  
  
 <span data-ttu-id="0f261-122">REPLICATE só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="0f261-122">REPLICATE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="0f261-123">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes que REPLICATE execute sua operação.</span><span class="sxs-lookup"><span data-stu-id="0f261-123">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before REPLICATE performs its operation.</span></span> <span data-ttu-id="0f261-124">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="0f261-124">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="0f261-125">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0f261-125">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="0f261-126">REPLICATE retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="0f261-126">REPLICATE returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0f261-127">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="0f261-127">Expression Examples</span></span>  
 <span data-ttu-id="0f261-128">Esse exemplo replica um literal de cadeia três vezes.</span><span class="sxs-lookup"><span data-stu-id="0f261-128">This example replicates a string literal three times.</span></span> <span data-ttu-id="0f261-129">O resultado de retorno é "Mountain BikeMountain BikeMountain Bike".</span><span class="sxs-lookup"><span data-stu-id="0f261-129">The return result is "Mountain BikeMountain BikeMountain Bike".</span></span>  
  
```  
REPLICATE("Mountain Bike", 3)  
```  
  
 <span data-ttu-id="0f261-130">Esse exemplo replica os valores na coluna **Nome** pelo valor na variável **Vezes** .</span><span class="sxs-lookup"><span data-stu-id="0f261-130">This example replicates values in the **Name** column by the value in the **Times** variable.</span></span> <span data-ttu-id="0f261-131">Se **Vezes** for 3 e **Nome** for Roda Dianteira de Passeio, o resultado de retorno será Roda Dianteira de PasseioRoda Dianteira de PasseioRoda Dianteira de Passeio.</span><span class="sxs-lookup"><span data-stu-id="0f261-131">If **Times** is 3 and **Name** is Touring Front Wheel, the return result is Touring Front WheelTouring Front WheelTouring Front Wheel.</span></span>  
  
```  
REPLICATE(Name, @Times)  
```  
  
 <span data-ttu-id="0f261-132">Esse exemplo replica o valor na variável **Nome** pelo valor na coluna **Vezes** .</span><span class="sxs-lookup"><span data-stu-id="0f261-132">This example replicates the value in the **Name** variable by the value in the **Times** column.</span></span> <span data-ttu-id="0f261-133">**Times** tem um tipo de dados não Integer e a expressão inclui uma conversão explícita para um tipo de dados Integer.</span><span class="sxs-lookup"><span data-stu-id="0f261-133">**Times** has a non-integer data type and the expression includes an explicit cast to an integer data type.</span></span> <span data-ttu-id="0f261-134">Se **Nome** contiver Capacete e **Vezes** for 2, o resultado de retorno será "CapaceteCapacete".</span><span class="sxs-lookup"><span data-stu-id="0f261-134">If **Name** contains Helmet and **Times** is 2, the return result is "HelmetHelmet".</span></span>  
  
```  
REPLICATE(@Name, (DT_I4(Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f261-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f261-135">See Also</span></span>  
 [<span data-ttu-id="0f261-136">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0f261-136">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
