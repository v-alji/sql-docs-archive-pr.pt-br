---
title: GETDATE (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0acb384a8c3c3dfdae55c7172f341f9e32765e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572606"
---
# <a name="getdate-ssis-expression"></a><span data-ttu-id="bdfee-102">GETDATE (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="bdfee-102">GETDATE (SSIS Expression)</span></span>
  <span data-ttu-id="bdfee-103">Retorna a data atual do sistema em um formato DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="bdfee-103">Returns the current date of the system in a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="bdfee-104">A função GETDATE não usa nenhum argumento.</span><span class="sxs-lookup"><span data-stu-id="bdfee-104">The GETDATE function takes no arguments.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdfee-105">O comprimento do resultado de retorno da função GETDATE é de 29 caracteres.</span><span class="sxs-lookup"><span data-stu-id="bdfee-105">The length of the return result from the GETDATE function is 29 characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfee-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bdfee-106">Syntax</span></span>  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="bdfee-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bdfee-107">Arguments</span></span>  
 <span data-ttu-id="bdfee-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="bdfee-108">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bdfee-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="bdfee-109">Result Types</span></span>  
 <span data-ttu-id="bdfee-110">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="bdfee-110">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="bdfee-111">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="bdfee-111">Expression Examples</span></span>  
 <span data-ttu-id="bdfee-112">Este exemplo retorna o ano da data atual.</span><span class="sxs-lookup"><span data-stu-id="bdfee-112">This example returns the year of the current date.</span></span>  
  
```  
DATEPART("year",GETDATE())  
```  
  
 <span data-ttu-id="bdfee-113">Este exemplo retorna o número de dias entre uma data na coluna **ModifiedDate** e a data atual.</span><span class="sxs-lookup"><span data-stu-id="bdfee-113">This example returns the number of days between a date in the **ModifiedDate** column and the current date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 <span data-ttu-id="bdfee-114">Este exemplo acrescenta três meses à data atual.</span><span class="sxs-lookup"><span data-stu-id="bdfee-114">This example adds three months to the current date.</span></span>  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdfee-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bdfee-115">See Also</span></span>  
 <span data-ttu-id="bdfee-116">[GETUTCDATE &#40;Expressão do SSIS&#41;](getutcdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="bdfee-116">[GETUTCDATE &#40;SSIS Expression&#41;](getutcdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="bdfee-117">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="bdfee-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
