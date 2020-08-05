---
title: MONTH (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], MONTH
- MONTH function
ms.assetid: b5a47a11-c2ef-49bd-bd70-235632ff7bf6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1f56906b4d25f2ba01f54fbdbc404d2c9ae4704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573201"
---
# <a name="month-ssis-expression"></a><span data-ttu-id="308b6-102">MONTH (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="308b6-102">MONTH (SSIS Expression)</span></span>
  <span data-ttu-id="308b6-103">Retorna um número inteiro que representa a parte do mês de uma data.</span><span class="sxs-lookup"><span data-stu-id="308b6-103">Returns an integer that represents the month datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="308b6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="308b6-104">Syntax</span></span>  
  
```  
  
MONTH(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="308b6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="308b6-105">Arguments</span></span>  
 <span data-ttu-id="308b6-106">*date*</span><span class="sxs-lookup"><span data-stu-id="308b6-106">*date*</span></span>  
 <span data-ttu-id="308b6-107">É uma data em qualquer formato de data.</span><span class="sxs-lookup"><span data-stu-id="308b6-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="308b6-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="308b6-108">Result Types</span></span>  
 <span data-ttu-id="308b6-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="308b6-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="308b6-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="308b6-110">Remarks</span></span>  
 <span data-ttu-id="308b6-111">MONTH retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="308b6-111">MONTH returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="308b6-112">Um literal de data deve ser convertido explicitamente em um dos tipos de dados de data.</span><span class="sxs-lookup"><span data-stu-id="308b6-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="308b6-113">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="308b6-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="308b6-114">A expressão não é validada quando um literal de data é convertido explicitamente em um destes tipos de dados de data: DT_DBTIMESTAMPOFFSET e DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="308b6-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="308b6-115">A função MONTH é mais resumida, mas equivale a usar DATEPART ("Mês", data).</span><span class="sxs-lookup"><span data-stu-id="308b6-115">Using the MONTH function is briefer but equivalent to using DATEPART("Month", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="308b6-116">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="308b6-116">Expression Examples</span></span>  
 <span data-ttu-id="308b6-117">Este exemplo retorna o número do mês em um literal de data.</span><span class="sxs-lookup"><span data-stu-id="308b6-117">This example returns the number of the month in a date literal.</span></span> <span data-ttu-id="308b6-118">Se a data estiver no formato "mm/dd/aaaa", este exemplo retornará 11.</span><span class="sxs-lookup"><span data-stu-id="308b6-118">If the date is in "mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
MONTH((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="308b6-119">Este exemplo retorna o inteiro que representa o mês na coluna **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="308b6-119">This example returns the integer that represents the month in the **ModifiedDate** column.</span></span>  
  
```  
MONTH(ModifiedDate)  
```  
  
 <span data-ttu-id="308b6-120">Este exemplo retorna o inteiro que representa o mês da data atual.</span><span class="sxs-lookup"><span data-stu-id="308b6-120">This example returns the integer that represents the month of the current date.</span></span>  
  
```  
MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="308b6-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="308b6-121">See Also</span></span>  
 <span data-ttu-id="308b6-122">[DATEADD &#40;Expressão do SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="308b6-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="308b6-123">[DATEDIFF &#40;Expressão do SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="308b6-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="308b6-124">[DATEPART &#40;Expressão do SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="308b6-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="308b6-125">[DAY &#40;Expressão do SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="308b6-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="308b6-126">[YEAR &#40;Expressão do SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="308b6-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="308b6-127">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="308b6-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
