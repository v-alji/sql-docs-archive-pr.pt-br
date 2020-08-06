---
title: ISNULL (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- null values [Integration Services]
- ISNULL function
ms.assetid: 88dbf49e-1307-4dda-b9db-ff1632053550
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 51eda21b5c9b85c5f9cfd613d0d92df9729fe620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681030"
---
# <a name="isnull-ssis-expression"></a><span data-ttu-id="6ba82-102">ISNULL (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="6ba82-102">ISNULL (SSIS Expression)</span></span>
  <span data-ttu-id="6ba82-103">Retorna um resultado booliano, baseando-se em se uma expressão é nula.</span><span class="sxs-lookup"><span data-stu-id="6ba82-103">Returns a Boolean result based on whether an expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ba82-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6ba82-104">Syntax</span></span>  
  
```  
  
ISNULL(expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ba82-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6ba82-105">Arguments</span></span>  
 <span data-ttu-id="6ba82-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="6ba82-106">*expression*</span></span>  
 <span data-ttu-id="6ba82-107">É uma expressão válida de qualquer tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="6ba82-107">Is a valid expression of any data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6ba82-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="6ba82-108">Result Types</span></span>  
 <span data-ttu-id="6ba82-109">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="6ba82-109">DT_BOOL</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="6ba82-110">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="6ba82-110">Expression Examples</span></span>  
 <span data-ttu-id="6ba82-111">Este exemplo retornará TRUE se a coluna **DiscontinuedDate** contiver um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="6ba82-111">This example returns TRUE if the **DiscontinuedDate** column contains a null value.</span></span>  
  
```  
ISNULL(DiscontinuedDate)  
```  
  
 <span data-ttu-id="6ba82-112">Este exemplo retornará "Sobrenome desconhecido" se o valor na coluna **LastName** for nulo; caso contrário ele retornará o valor em **LastName**.</span><span class="sxs-lookup"><span data-stu-id="6ba82-112">This example returns "Unknown last name" if the value in the **LastName** column is null, otherwise it returns the value in **LastName**.</span></span>  
  
```  
ISNULL(LastName)? "Unknown last name":LastName  
```  
  
 <span data-ttu-id="6ba82-113">Este exemplo sempre retorna TRUE se a coluna **DaysToManufacture** for nula, independentemente do valor da variável **AddDays**.</span><span class="sxs-lookup"><span data-stu-id="6ba82-113">This example always returns TRUE if the **DaysToManufacture** column is null, regardless of the value of the variable **AddDays**.</span></span>  
  
```  
ISNULL(DaysToManufacture + @AddDays)  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ba82-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ba82-114">See Also</span></span>  
 <span data-ttu-id="6ba82-115">[Funções &#40;Expressão do SSIS&#41;](functions-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6ba82-115">[Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md) </span></span>  
 [<span data-ttu-id="6ba82-116">COALESCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ba82-116">COALESCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/coalesce-transact-sql)  
  
  
