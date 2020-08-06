---
title: REPLACE (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- replacing string expression
- REPLACE function
ms.assetid: a6837043-ea70-4c6a-9c7a-6868b02b2adc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e483ba6c9c72cb777f2955929a717c6c2e17a8c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681027"
---
# <a name="replace-ssis-expression"></a><span data-ttu-id="3ae02-102">REPLACE (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="3ae02-102">REPLACE (SSIS Expression)</span></span>
  <span data-ttu-id="3ae02-103">Retorna uma expressão de caractere depois de substituir uma cadeia de caracteres na expressão por uma cadeia diferente ou vazia.</span><span class="sxs-lookup"><span data-stu-id="3ae02-103">Returns a character expression after replacing a character string within the expression with either a different character string or an empty string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ae02-104">A função REPLACE geralmente usa cadeias de caracteres longos.</span><span class="sxs-lookup"><span data-stu-id="3ae02-104">The REPLACE function frequently uses long strings.</span></span> <span data-ttu-id="3ae02-105">As consequências do truncamento podem ser controladas muito bem ou causam um aviso ou um erro.</span><span class="sxs-lookup"><span data-stu-id="3ae02-105">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="3ae02-106">Para obter mais informações, consulte [Sintaxe &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="3ae02-106">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ae02-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3ae02-107">Syntax</span></span>  
  
```  
  
REPLACE(character_expression,searchstring,replacementstring)  
```  
  
## <a name="arguments"></a><span data-ttu-id="3ae02-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3ae02-108">Arguments</span></span>  
 <span data-ttu-id="3ae02-109">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="3ae02-109">*character_expression*</span></span>  
 <span data-ttu-id="3ae02-110">É uma expressão de caractere válida que a função pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3ae02-110">Is a valid character expression that the function searches.</span></span>  
  
 <span data-ttu-id="3ae02-111">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="3ae02-111">*searchstring*</span></span>  
 <span data-ttu-id="3ae02-112">É uma expressão de caractere válida que a função tenta localizar.</span><span class="sxs-lookup"><span data-stu-id="3ae02-112">Is a valid character expression that the function attempts to locate.</span></span>  
  
 <span data-ttu-id="3ae02-113">*replacementstring*</span><span class="sxs-lookup"><span data-stu-id="3ae02-113">*replacementstring*</span></span>  
 <span data-ttu-id="3ae02-114">É uma expressão de caractere válida que é a expressão de substituição.</span><span class="sxs-lookup"><span data-stu-id="3ae02-114">Is a valid character expression that is the replacement expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3ae02-115">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="3ae02-115">Result Types</span></span>  
 <span data-ttu-id="3ae02-116">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="3ae02-116">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ae02-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="3ae02-117">Remarks</span></span>  
 <span data-ttu-id="3ae02-118">O comprimento de *searchstring* não deve ser zero.</span><span class="sxs-lookup"><span data-stu-id="3ae02-118">The length of *searchstring* must not be zero.</span></span>  
  
 <span data-ttu-id="3ae02-119">O comprimento de *replacementstring* pode ser zero.</span><span class="sxs-lookup"><span data-stu-id="3ae02-119">The length of *replacementstring* may be zero.</span></span>  
  
 <span data-ttu-id="3ae02-120">Os argumentos *searchstring* e *replacementstring* podem usar variáveis e colunas.</span><span class="sxs-lookup"><span data-stu-id="3ae02-120">The *searchstring* and *replacementstring* arguments can use variables and columns.</span></span>  
  
 <span data-ttu-id="3ae02-121">REPLICATE funciona apenas com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="3ae02-121">REPLACE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="3ae02-122">Os argumentos*character_expression1, character_expression2,* e *character_expression3* , que são literais de cadeia de caracteres ou colunas de dados com o tipo de dados DT_STR, são implicitamente convertidos para o tipo de dados DT_WSTR antes de REPLACE executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="3ae02-122">*character_expression1, character_expression2,* and *character_expression3* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before REPLACE performs its operation.</span></span> <span data-ttu-id="3ae02-123">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="3ae02-123">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="3ae02-124">Para obter mais informações, consulte [Cast &#40;Expressão do SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="3ae02-124">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="3ae02-125">REPLACE retornará um resultado nulo se qualquer argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="3ae02-125">REPLACE returns a null result if any argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3ae02-126">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="3ae02-126">Expression Examples</span></span>  
 <span data-ttu-id="3ae02-127">Este exemplo usa um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3ae02-127">This example uses a string literal.</span></span> <span data-ttu-id="3ae02-128">O resultado de retorno é “Toda Bicicleta de Terreno”.</span><span class="sxs-lookup"><span data-stu-id="3ae02-128">The return result is "All Terrain Bike".</span></span>  
  
```  
REPLACE("Mountain Bike", "Mountain","All Terrain")  
```  
  
 <span data-ttu-id="3ae02-129">Este exemplo remove a cadeia de caracteres "Bike" da coluna **Product** .</span><span class="sxs-lookup"><span data-stu-id="3ae02-129">This example removes the string "Bike" from the **Product** column.</span></span>  
  
```  
REPLACE(Product, "Bike","")  
```  
  
 <span data-ttu-id="3ae02-130">Este exemplo substitui valores na coluna **DaysToManufacture** .</span><span class="sxs-lookup"><span data-stu-id="3ae02-130">This example replaces values in the **DaysToManufacture** column.</span></span> <span data-ttu-id="3ae02-131">A coluna tem um tipo de dados Integer e a expressão inclui conversão de **DaysToManufacture** para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="3ae02-131">The column has an integer data type and the expression includes casting **DaysToManufacture** to the DT_WSTR data type.</span></span>  
  
```  
REPLACE((DT_WSTR,8)DaysToManufacture,"6","5")  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ae02-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ae02-132">See Also</span></span>  
 <span data-ttu-id="3ae02-133">[SUBSTRING &#40;Expressão SSIS&#41;](substring-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="3ae02-133">[SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md) </span></span>  
 [<span data-ttu-id="3ae02-134">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3ae02-134">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
