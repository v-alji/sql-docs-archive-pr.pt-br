---
title: Análise rápida | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- fast parse [Integration Services]
ms.assetid: 6688707d-3c5b-404e-aa2f-e13092ac8d95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 343b8b8b74338512dbf29b3d2efd436df1ffa8ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683120"
---
# <a name="fast-parse"></a><span data-ttu-id="e1176-102">Fast Parse</span><span class="sxs-lookup"><span data-stu-id="e1176-102">Fast Parse</span></span>
  <span data-ttu-id="e1176-103">A análise rápida fornece um conjunto de rotinas simples e rápidas para analisar dados.</span><span class="sxs-lookup"><span data-stu-id="e1176-103">Fast parse provides a fast, simple set of routines for parsing data.</span></span> <span data-ttu-id="e1176-104">Essas rotinas não são sensíveis à localidade e aceitam apenas um subconjunto de formatos de data, hora e inteiro.</span><span class="sxs-lookup"><span data-stu-id="e1176-104">These routines are not locale-sensitive and they support only a subset of date, time, and integer formats.</span></span>  
  
## <a name="requirements-and-limitations"></a><span data-ttu-id="e1176-105">Requisitos e limitações</span><span class="sxs-lookup"><span data-stu-id="e1176-105">Requirements and Limitations</span></span>  
 <span data-ttu-id="e1176-106">Ao se implementar a análise rápida, o pacote perde sua habilidade para interpretar data, hora e dados numéricos em formatos específicos à localidade e em formatos ISO 8601 básicos e estendidos, mas o pacote melhora seu desempenho.</span><span class="sxs-lookup"><span data-stu-id="e1176-106">By implementing fast parse, a package forfeits its ability to interpret date, time, and numeric data in locale-specific formats and many frequently used ISO 8601 basic and extended formats, but the package enhances its performance.</span></span> <span data-ttu-id="e1176-107">Por exemplo, a análise rápida oferece suporte somente aos formatos mais comuns utilizados para representar data como YYYYMMDD e YYYY-MM-DD, não executa análise específica do local, não reconhece caracteres especiais em dados de moeda e não pode converter representação hexadecimal ou científica de inteiros.</span><span class="sxs-lookup"><span data-stu-id="e1176-107">For example, fast parse supports only the most commonly used date format representations such as YYYYMMDD and YYYY-MM-DD, does not perform locale-specific parsing, does not recognize special characters in currency data, and cannot convert hexadecimal or scientific representation of integers.</span></span>  
  
 <span data-ttu-id="e1176-108">A análise rápida só está disponível quando você usa o fonte Arquivo Simples ou a transformação de Conversão de Dados.</span><span class="sxs-lookup"><span data-stu-id="e1176-108">Fast parse is available only when you use the Flat File source or the Data Conversion transformation.</span></span> <span data-ttu-id="e1176-109">O aumento no desempenho pode ser significativo e você pode considerar o uso da análise rápida nesses componentes de fluxo de dados se desejar.</span><span class="sxs-lookup"><span data-stu-id="e1176-109">The increase in performance can be significant, and you should consider using fast parse in these data flow components if you can.</span></span>  
  
 <span data-ttu-id="e1176-110">Se o fluxo de dados no pacote requer análise sensível a localidade, a análise padrão é recomendada em lugar da análise rápida.</span><span class="sxs-lookup"><span data-stu-id="e1176-110">If the data flow in the package requires locale-sensitive parsing, standard parse is recommended instead of fast parse.</span></span> <span data-ttu-id="e1176-111">Por exemplo, a análise rápida não reconhece dados sensíveis ao local, que incluem símbolos decimais como a vírgula, formatos de data que não sejam ano-mês-dia e símbolos de moeda.</span><span class="sxs-lookup"><span data-stu-id="e1176-111">For example, fast parse does not recognize locale-sensitive data that includes decimal symbols such as the comma, date formats other than year-month-date formats, and currency symbols.</span></span>  
  
 <span data-ttu-id="e1176-112">Representações truncadas que implicam em uma ou mais partes da data, como um século, um ano ou um mês, não são reconhecidas pela análise rápida.</span><span class="sxs-lookup"><span data-stu-id="e1176-112">Truncated representations that imply one or more date parts, such as a century, a year, or a month, are not recognized by fast parse.</span></span> <span data-ttu-id="e1176-113">Por exemplo, a análise rápida não reconhece o formato '**-YYMM**', que especifica um ano e um mês em um século implícito, nem '**--MM**', que especifica um mês em um ano implícito.</span><span class="sxs-lookup"><span data-stu-id="e1176-113">For example, fast parse recognizes neither the '**-YYMM**' format, which specifies a year and month in an implied century, nor '**--MM**', which specifies a month in an implied year.</span></span> <span data-ttu-id="e1176-114">Porém, algumas representações com precisão reduzida são reconhecidas.</span><span class="sxs-lookup"><span data-stu-id="e1176-114">However, some representations with reduced precision are recognized.</span></span> <span data-ttu-id="e1176-115">Por exemplo, a análise rápida reconhece o formato 'hhmm;', que indica somente hora e minuto e '**YYYY**', que indica somente o ano.</span><span class="sxs-lookup"><span data-stu-id="e1176-115">For example, fast parse recognizes the 'hhmm;' format, which indicates hour and minute only, and '**YYYY**', which indicates year only.</span></span>  
  
 <span data-ttu-id="e1176-116">A análise rápida é especificada ao nível de coluna.</span><span class="sxs-lookup"><span data-stu-id="e1176-116">Fast parse is specified at the column level.</span></span> <span data-ttu-id="e1176-117">Na fonte Flat File e na transformação de Conversão de Dados, você pode especificar a Análise rápida nas colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="e1176-117">In the Flat File source and the Data Conversion transformation, you can specify Fast parse on output columns.</span></span> <span data-ttu-id="e1176-118">Entradas e saídas podem incluir colunas sensíveis a local e colunas não sensíveis a local.</span><span class="sxs-lookup"><span data-stu-id="e1176-118">Inputs and outputs can include both locale-sensitive and locale-insensitive columns.</span></span>  
  
 <span data-ttu-id="e1176-119">Para obter mais informações sobre os formatos de dados suportados pela Análise Rápida, veja [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) e [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="e1176-119">For more information about the data formats that Fast parse supports, see [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) and [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e1176-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e1176-120">Related Tasks</span></span>  
 [<span data-ttu-id="e1176-121">Definir a análise rápida</span><span class="sxs-lookup"><span data-stu-id="e1176-121">Set Fast Parse</span></span>](../../2014/integration-services/set-fast-parse.md)  
  
  
