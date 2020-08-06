---
title: Análise de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parsing [Integration Services]
- data parsing [Integration Services]
ms.assetid: 8893ea9d-634c-4309-b52c-6337222dcb39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bd34cd83351e31313ae96ff5709ec999a60f2f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571480"
---
# <a name="parsing-data"></a><span data-ttu-id="77906-102">Análise de dados</span><span class="sxs-lookup"><span data-stu-id="77906-102">Parsing Data</span></span>
  <span data-ttu-id="77906-103">Os fluxos de dados em pacotes extraem e carregam dados entre armazenamentos de dados heterogêneos, que podem usar uma variedade de tipos de dados padrão e personalizados.</span><span class="sxs-lookup"><span data-stu-id="77906-103">Data flows in packages extract and load data between heterogeneous data stores, which may use a variety of standard and custom data types.</span></span> <span data-ttu-id="77906-104">Em um fluxo de dados, as fontes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fazem o trabalho de extração dos dados, análise dos dados da cadeia de caracteres e conversão de dados para um tipo de dados [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77906-104">In a data flow, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources do the work of extracting data, parsing string data, and converting data to an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type.</span></span> <span data-ttu-id="77906-105">As transformações subsequentes podem analisar os dados para convertê-los em um tipo diferente de dados ou para criar cópias de coluna com tipos diferentes de dados.</span><span class="sxs-lookup"><span data-stu-id="77906-105">Subsequent transformations may parse data to convert it to a different data type, or create column copies with different data types.</span></span> <span data-ttu-id="77906-106">As expressões usadas em componentes também podem lançar argumentos e operandos para os tipos diferentes de dados.</span><span class="sxs-lookup"><span data-stu-id="77906-106">Expressions used in components may also cast arguments and operands to different data types.</span></span> <span data-ttu-id="77906-107">Finalmente, quando os dados são carregados no repositório de dados, o destino pode analisar os dados para convertê-los em um tipo de dados usado pelo destino.</span><span class="sxs-lookup"><span data-stu-id="77906-107">Finally, when the data is loaded into a data store, the destination may parse the data to convert it to a data type that the destination uses.</span></span> <span data-ttu-id="77906-108">Para obter mais informações, consulte [Integration Services Data Types](integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="77906-108">For more information, see [Integration Services Data Types](integration-services-data-types.md).</span></span>  
  
## <a name="types-of-parsing"></a><span data-ttu-id="77906-109">Tipos de análise</span><span class="sxs-lookup"><span data-stu-id="77906-109">Types of Parsing</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="77906-110">fornece dois tipos de análises para conversão de dados: Análise rápida e Análise padrão.</span><span class="sxs-lookup"><span data-stu-id="77906-110">provides two types of parsing for converting data: Fast parse and Standard parse.</span></span>  
  
-   <span data-ttu-id="77906-111">A análise rápida é um conjunto simples de rotinas de análise que não oferece suporte a conversões de tipos de dados específicas de localidade, e só oferece suporte aos formatos de data e hora usados com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="77906-111">Fast parse is a fast, simple set of parsing routines that does not support locale-specific data type conversions, and supports only the most frequently used date and time formats.</span></span> <span data-ttu-id="77906-112">Para obter mais informações, consulte [Fast Parse](../fast-parse.md).</span><span class="sxs-lookup"><span data-stu-id="77906-112">For more information, see [Fast Parse](../fast-parse.md).</span></span>  
  
-   <span data-ttu-id="77906-113">A análise padrão é um conjunto rico de rotinas de análise que oferecem suporte a todas as conversões de tipos de dados fornecidas pelas APIs de conversão de tipos de dados de Automação, disponíveis no Oleaut32.dll e Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="77906-113">Standard parse is a rich set of parsing routines that supports all the data type conversions that are provided by the Automation data type conversion APIs available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="77906-114">Para obter mais informações, consulte [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="77906-114">For more information, see [Standard Parse](../standard-parse.md).</span></span>  
  
  
