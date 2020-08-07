---
title: Truncamento de dados (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- truncating data
- data truncation [Integration Services]
- expressions [Integration Services], data truncation
- truncate options [Integration Services]
ms.assetid: 02461e15-49ca-445b-abb3-5c369c283ec2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0c4280c9eacd22ebf84bf1570d485de51cab09b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583175"
---
# <a name="data-truncation-ssis"></a><span data-ttu-id="bb5a2-102">Truncamento de dados (SSIS)</span><span class="sxs-lookup"><span data-stu-id="bb5a2-102">Data Truncation (SSIS)</span></span>
  <span data-ttu-id="bb5a2-103">Uma expressão pode fazer com que os dados sejam truncados inadvertidamente.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-103">An expression may inadvertently cause data to be truncated.</span></span> <span data-ttu-id="bb5a2-104">O truncamento pode ocorrer nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="bb5a2-104">Truncation can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="bb5a2-105">cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-105">Strings.</span></span> <span data-ttu-id="bb5a2-106">Por exemplo, a conversão de dados da cadeia de caracteres com um tipo de dados DT_WSTR para uma cadeia de caracteres com o mesmo comprimento, medido em caracteres, com um tipo de dados DT_STR causa perda de dados, se a cadeia de caracteres original contém caracteres de byte duplo.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-106">For example, translating string data with a DT_WSTR data type to the same length string, measured in characters, with a DT_STR data type causes data loss if the original string contains double-byte characters.</span></span>  
  
-   <span data-ttu-id="bb5a2-107">Dígitos significantes.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-107">Significant digits.</span></span> <span data-ttu-id="bb5a2-108">Por exemplo, a conversão de um inteiro de um tipo de dados DT_I4 para um tipo de dados DT_I2 ou de um inteiro não assinado para um inteiro assinado.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-108">For example, casting an integer from a DT_I4 data type to a DT_I2 data type or an unsigned integer to a signed integer.</span></span>  
  
-   <span data-ttu-id="bb5a2-109">Dígitos insignificantes.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-109">Insignificant digits.</span></span> <span data-ttu-id="bb5a2-110">Por exemplo, a conversão de um número real de DT_R8 para um DT_R4 ou de um inteiro de um tipo de dados DT_I4 para um tipo de dados DT_R4.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-110">For example, casting a real number from a DT_R8 to a DT_R4 or an integer from a DT_I4 data type to a DT_R4 data type.</span></span>  
  
 <span data-ttu-id="bb5a2-111">O avaliador de expressão identifica conversões explícitas que podem causar truncamento e emite um aviso quando a expressão é analisada.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-111">The expression evaluator identifies explicit casts that may cause truncation and issues a warning when the expression is parsed.</span></span> <span data-ttu-id="bb5a2-112">Por exemplo, o avaliador de expressão o advertirá se uma cadeia de 30 caracteres for convertida em uma cadeia de 20 caracteres.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-112">For example, the expression evaluator warns you if a 30-character string is cast into a 20-character string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb5a2-113">O truncamento não é verificado no tempo de execução; dados são truncados sem aviso.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-113">Truncation is not checked at run time; data is truncated without warning.</span></span> <span data-ttu-id="bb5a2-114">Porém, a maioria dos adaptadores e das transformações de dados aceita saídas de erro que podem controlar a disposição de linhas de erro.</span><span class="sxs-lookup"><span data-stu-id="bb5a2-114">However, most data adapters and transformations support error outputs that can handle the disposition of error rows.</span></span> <span data-ttu-id="bb5a2-115">Para obter mais informações sobre como lidar com truncamento de dados, consulte [tratamento de erros em dados](../data-flow/error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="bb5a2-115">For more information about handling truncation of data, see [Error Handling in Data](../data-flow/error-handling-in-data.md).</span></span>  
  
  
