---
title: Formatos de dados numéricos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- integer data types [Integration Services]
- numeric data formats for fast parse
- locale-sensitive parsing [Integration Services]
- fast parse [Integration Services]
ms.assetid: fa3975ce-9d21-408a-857d-f85e30af27b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc54a331c3762e31ba9d9a431aaca7eda6374d8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574095"
---
# <a name="numeric-data-formats"></a><span data-ttu-id="f7f9a-102">Formatos de dados numéricos</span><span class="sxs-lookup"><span data-stu-id="f7f9a-102">Numeric Data Formats</span></span>
  <span data-ttu-id="f7f9a-103">A análise rápida fornece uma análise de dados rápida e simples a um conjunto de rotinas sem diferenciação de localidade.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-103">Fast parse provides a fast, simple, locale-insensitive set of routines for parsing data.</span></span> <span data-ttu-id="f7f9a-104">A análise rápida suporta apenas um conjunto limitado de formatos para tipos de dados de números inteiros.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-104">Fast parse supports only a limited set of formats for integer data types.</span></span>  
  
## <a name="integer-data-types"></a><span data-ttu-id="f7f9a-105">Tipos de Dados de Números Inteiros</span><span class="sxs-lookup"><span data-stu-id="f7f9a-105">Integer Data Types</span></span>  
 <span data-ttu-id="f7f9a-106">Os tipos de dados de números inteiros que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fornece são DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8 e DT_UI8.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-106">The integer data types that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides are DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8, and DT_UI8.</span></span> <span data-ttu-id="f7f9a-107">Para obter mais informações, consulte [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f7f9a-107">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="f7f9a-108">A análise rápida suporta os seguintes formatos para tipos de dados de números inteiros:</span><span class="sxs-lookup"><span data-stu-id="f7f9a-108">Fast parse supports the following formats for integer data types:</span></span>  
  
-   <span data-ttu-id="f7f9a-109">Zero com espaços à esquerda e à direita ou paradas de tabulação.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-109">Zero or more leading and trailing spaces or tab stops.</span></span> <span data-ttu-id="f7f9a-110">Por exemplo, o valor "  123  " é válido.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-110">For example, the value "  123  " is valid.</span></span> <span data-ttu-id="f7f9a-111">Um valor com espaços é avaliado como zero.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-111">A value that is all spaces evaluates to zero.</span></span>  
  
-   <span data-ttu-id="f7f9a-112">Um sinal de mais, menos ou nenhum sinal.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-112">A leading plus sign, minus sign, or neither.</span></span> <span data-ttu-id="f7f9a-113">Por exemplo, os valores +123, -123 e 123 são válidos.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-113">For example, the values +123, -123, and 123 are valid.</span></span>  
  
-   <span data-ttu-id="f7f9a-114">Um ou mais números hindu-árabes (0-9).</span><span class="sxs-lookup"><span data-stu-id="f7f9a-114">One or more Hindu-Arabic numerals (0-9).</span></span> <span data-ttu-id="f7f9a-115">Por exemplo, o valor 345 é válido.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-115">For example, the value 345 is valid.</span></span> <span data-ttu-id="f7f9a-116">Outros dados numéricos do idioma não são suportados.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-116">Other language numerals are not supported.</span></span>  
  
 <span data-ttu-id="f7f9a-117">Entre os formatos de dados que não são suportados estão:</span><span class="sxs-lookup"><span data-stu-id="f7f9a-117">Non-supported data formats include the following:</span></span>  
  
-   <span data-ttu-id="f7f9a-118">Caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-118">Special characters.</span></span> <span data-ttu-id="f7f9a-119">Por exemplo, o símbolo de cifrão ($) não é suportado e o valor $20 não pode ser analisado.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-119">For example, the currency character $ is not supported, and the value $20 cannot be parsed.</span></span>  
  
-   <span data-ttu-id="f7f9a-120">Caracteres com espaço em branco como quebra de linha, retornos de carro e espaços que não indicam uma quebra.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-120">White-space characters such as line feed, carriage returns, and non-breaking spaces.</span></span> <span data-ttu-id="f7f9a-121">Por exemplo, o valor " 123" não pode ser analisado.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-121">For example, the value " 123" cannot be parsed.</span></span>  
  
-   <span data-ttu-id="f7f9a-122">Representações hexadecimais de números inteiros.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-122">Hexadecimal representations of integers.</span></span> <span data-ttu-id="f7f9a-123">Por exemplo, o valor 2EE não pode ser analisado.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-123">For example, the value 2EE cannot be parsed.</span></span>  
  
-   <span data-ttu-id="f7f9a-124">Representação de notação científica de números inteiros.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-124">Scientific notation representation of integers.</span></span> <span data-ttu-id="f7f9a-125">Por exemplo, o valor 1E+10 não pode ser analisado.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-125">For example, the value 1E+10 cannot be parsed.</span></span>  
  
 <span data-ttu-id="f7f9a-126">Os seguintes formatos são formatos de dados de saída para números inteiros:</span><span class="sxs-lookup"><span data-stu-id="f7f9a-126">The following formats are output data formats for integers:</span></span>  
  
-   <span data-ttu-id="f7f9a-127">Um sinal de menos para números negativos e nenhum sinal para números positivos.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-127">A minus sign for negative numbers and nothing for positive ones.</span></span>  
  
-   <span data-ttu-id="f7f9a-128">Nenhum espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="f7f9a-128">No white spaces.</span></span>  
  
-   <span data-ttu-id="f7f9a-129">Um ou mais números hindu-árabes (0-9).</span><span class="sxs-lookup"><span data-stu-id="f7f9a-129">One or more Hindu-Arabic numerals (0-9).</span></span>  
  
  
