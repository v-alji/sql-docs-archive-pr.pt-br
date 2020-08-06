---
title: GETUTCDATE (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], GETUTCDATE
- current date
- UTC time
- GETUTCDATE function
ms.assetid: 2282339c-c24f-493e-8e66-181ea8af5ad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f157ab5641e521a42cb3c96c96446b31de5dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681042"
---
# <a name="getutcdate-ssis-expression"></a><span data-ttu-id="7e933-102">GETUTCDATE (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="7e933-102">GETUTCDATE (SSIS Expression)</span></span>
  <span data-ttu-id="7e933-103">Retorna a data atual do sistema na hora UTC (Universal Time Coordinate ou Greenwich Mean Time) por meio de um formato DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="7e933-103">Returns the current date of the system in UTC time (Universal Time Coordinate or Greenwich Mean Time) using a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="7e933-104">A função GETUTCDATE não pega nenhum argumento.</span><span class="sxs-lookup"><span data-stu-id="7e933-104">The GETUTCDATE function takes no arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e933-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7e933-105">Syntax</span></span>  
  
```  
  
GETUTCDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="7e933-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7e933-106">Arguments</span></span>  
 <span data-ttu-id="7e933-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7e933-107">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7e933-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="7e933-108">Result Types</span></span>  
 <span data-ttu-id="7e933-109">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="7e933-109">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7e933-110">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="7e933-110">Expression Examples</span></span>  
 <span data-ttu-id="7e933-111">Este exemplo retorna o ano da data atual em hora de UTC.</span><span class="sxs-lookup"><span data-stu-id="7e933-111">This example returns the year of the current date in UTC time.</span></span>  
  
```  
DATEPART("year",GETUTCDATE())  
```  
  
 <span data-ttu-id="7e933-112">Este exemplo retorna o número de dias entre uma data na coluna **ModifiedDate** e a data atual em UTC.</span><span class="sxs-lookup"><span data-stu-id="7e933-112">This example returns the number of days between a date in the **ModifiedDate** column and the current UTC date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETUTCDATE())  
```  
  
 <span data-ttu-id="7e933-113">Este exemplo acrescenta três meses à data atual em UTC.</span><span class="sxs-lookup"><span data-stu-id="7e933-113">This example adds three months to the current UTC date.</span></span>  
  
```  
DATEADD("Month",3,GETUTCDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e933-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e933-114">See Also</span></span>  
 <span data-ttu-id="7e933-115">[GETDATE &#40;Expressão do SSIS&#41;](getdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7e933-115">[GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="7e933-116">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7e933-116">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
