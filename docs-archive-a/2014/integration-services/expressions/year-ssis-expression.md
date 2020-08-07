---
title: YEAR (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], YEAR
- YEAR function
ms.assetid: 9d88dead-ace8-44b9-b8e2-916c1842e155
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181375d489fbf7abf0718386efacf4167ba555d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581446"
---
# <a name="year-ssis-expression"></a><span data-ttu-id="fb397-102">YEAR (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="fb397-102">YEAR (SSIS Expression)</span></span>
  <span data-ttu-id="fb397-103">Retorna um inteiro que representa o ano da parte da data.</span><span class="sxs-lookup"><span data-stu-id="fb397-103">Returns an integer that represents the year datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb397-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fb397-104">Syntax</span></span>  
  
```  
  
YEAR(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb397-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fb397-105">Arguments</span></span>  
 <span data-ttu-id="fb397-106">*date*</span><span class="sxs-lookup"><span data-stu-id="fb397-106">*date*</span></span>  
 <span data-ttu-id="fb397-107">É uma data em qualquer formato de data.</span><span class="sxs-lookup"><span data-stu-id="fb397-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fb397-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="fb397-108">Result Types</span></span>  
 <span data-ttu-id="fb397-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="fb397-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb397-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="fb397-110">Remarks</span></span>  
 <span data-ttu-id="fb397-111">YEAR retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="fb397-111">YEAR returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="fb397-112">Um literal de data deve ser convertido explicitamente em um dos tipos de dados de data.</span><span class="sxs-lookup"><span data-stu-id="fb397-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="fb397-113">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fb397-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb397-114">A expressão não é validada quando um literal de data é convertido explicitamente em um destes tipos de dados de data: DT_DBTIMESTAMPOFFSET e DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="fb397-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="fb397-115">A função YEAR é mais resumida, mas equivale a usar a função DATEPART ("Ano", data).</span><span class="sxs-lookup"><span data-stu-id="fb397-115">Using the YEAR function is briefer but equivalent to using the DATEPART("Year", date) function.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="fb397-116">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="fb397-116">Expression Examples</span></span>  
 <span data-ttu-id="fb397-117">Este exemplo retorna o número do ano em um literal de data.</span><span class="sxs-lookup"><span data-stu-id="fb397-117">This example returns the number of the year in a date literal.</span></span> <span data-ttu-id="fb397-118">Se a data estiver no formato mm/dd/aaaa, este exemplo retornará "2002".</span><span class="sxs-lookup"><span data-stu-id="fb397-118">If the date is in mm/dd/yyyy format, this example returns "2002".</span></span>  
  
```  
YEAR((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="fb397-119">Este exemplo retorna o inteiro que representa o ano na coluna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="fb397-119">This example returns the integer that represents the year in the **ModifiedDate** column.</span></span>  
  
```  
YEAR(ModifiedDate)  
```  
  
 <span data-ttu-id="fb397-120">Este exemplo retorna o inteiro que representa o ano da data atual.</span><span class="sxs-lookup"><span data-stu-id="fb397-120">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
YEAR(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb397-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb397-121">See Also</span></span>  
 <span data-ttu-id="fb397-122">[DATEADD &#40;Expressão do SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="fb397-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="fb397-123">[DATEDIFF &#40;Expressão do SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="fb397-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="fb397-124">[DATEPART &#40;Expressão do SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="fb397-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="fb397-125">[DAY &#40;Expressão do SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="fb397-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="fb397-126">[MONTH &#40;Expressão do SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="fb397-126">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 [<span data-ttu-id="fb397-127">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="fb397-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
