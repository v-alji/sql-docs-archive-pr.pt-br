---
title: Transformação Conversão de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontrans.f1
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: fd515bbc-6f49-4d0c-ae7f-6ea3c3f24a1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57b1f70c070cdf81dc0bc899ed365d048db26cc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569575"
---
# <a name="data-conversion-transformation"></a><span data-ttu-id="93011-102">transformação Conversão de Dados</span><span class="sxs-lookup"><span data-stu-id="93011-102">Data Conversion Transformation</span></span>
  <span data-ttu-id="93011-103">A transformação Conversão de Dados converte os dados de uma coluna de entrada em um tipo diferente de dados e os copia em uma nova coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="93011-103">The Data Conversion transformation converts the data in an input column to a different data type and then copies it to a new output column.</span></span> <span data-ttu-id="93011-104">Por exemplo, um pacote pode extrair dados de várias fontes e usar essa transformação para converter colunas em tipos de dados exigidos pelo armazenamento dos dados de destino.</span><span class="sxs-lookup"><span data-stu-id="93011-104">For example, a package can extract data from multiple sources, and then use this transformation to convert columns to the data type required by the destination data store.</span></span> <span data-ttu-id="93011-105">Você pode aplicar várias conversões em uma única coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="93011-105">You can apply multiple conversions to a single input column.</span></span>  
  
 <span data-ttu-id="93011-106">Usando essa transformação, um pacote pode executar os seguintes tipos de conversão de dados:</span><span class="sxs-lookup"><span data-stu-id="93011-106">Using this transformation, a package can perform the following types of data conversions:</span></span>  
  
-   <span data-ttu-id="93011-107">Alterar o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="93011-107">Change the data type.</span></span> <span data-ttu-id="93011-108">Para obter mais informações, consulte [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="93011-108">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93011-109">Se você estiver convertendo dados em um tipo de dados de data ou data/hora, a data na coluna de saída estará no formato ISO, embora a preferência de localidade possa especificar um formato diferente.</span><span class="sxs-lookup"><span data-stu-id="93011-109">If you are converting data to a date or a datetime data type, the date in the output column is in the ISO format, although the locale preference may specify a different format.</span></span>  
  
-   <span data-ttu-id="93011-110">Defina o comprimento da coluna dos dados da cadeia de caracteres e a precisão e a escala em dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="93011-110">Set the column length of string data and the precision and scale on numeric data.</span></span> <span data-ttu-id="93011-111">Para obter mais informações, consulte [Precisão, escala e comprimento &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="93011-111">For more information, see [Precision, Scale, and Length &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span></span>  
  
-   <span data-ttu-id="93011-112">Especifique uma página de código.</span><span class="sxs-lookup"><span data-stu-id="93011-112">Specify a code page.</span></span> <span data-ttu-id="93011-113">Para obter mais informações, consulte [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="93011-113">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93011-114">Ao copiar entre colunas com um tipo de dados de cadeia de caracteres, as duas colunas devem usar a mesma página de código.</span><span class="sxs-lookup"><span data-stu-id="93011-114">When copying between columns with a string data type, the two columns must use the same code page.</span></span>  
  
 <span data-ttu-id="93011-115">Se o comprimento de uma coluna de saída de dados de cadeia de caracteres for menor do que o comprimento de sua coluna de entrada correspondente, os dados de saída serão truncados.</span><span class="sxs-lookup"><span data-stu-id="93011-115">If the length of an output column of string data is shorter than the length of its corresponding input column, the output data is truncated.</span></span> <span data-ttu-id="93011-116">Para obter mais informações, consulte [Tratamento de erros em dados](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="93011-116">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="93011-117">Essa transformação tem uma entrada, uma saída e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="93011-117">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="93011-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="93011-118">Related Tasks</span></span>  
 <span data-ttu-id="93011-119">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="93011-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="93011-120">Para obter informações sobre como usar a transformação Conversão de Dados no Designer SSIS, consulte [Converter dados em um tipo de dados diferente por meio da transformação Conversão de Dados](data-conversion-transformation.md) e [Editor de Transformação Conversão de Dados](../../data-conversion-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="93011-120">For information about using the Data Conversion Transformation in the SSIS Designer, see [Convert Data to a Different Data Type by Using the Data Conversion Transformation](data-conversion-transformation.md) and [Data Conversion Transformation Editor](../../data-conversion-transformation-editor.md).</span></span> <span data-ttu-id="93011-121">Para obter informações sobre como definir as propriedades dessa transformação programaticamente, consulte [Propriedades comuns](../../common-properties.md) e [Propriedades personalizadas de Transformação](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="93011-121">For information about setting properties of this transformation programmatically, see [Common Properties](../../common-properties.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="93011-122">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="93011-122">Related Content</span></span>  
 <span data-ttu-id="93011-123">Entrada de blog, [Comparação de desempenho entre as técnicas de conversão de tipo de dados no SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="93011-123">Blog entry, [Performance Comparison between Data Type Conversion Techniques in SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93011-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="93011-124">See Also</span></span>  
 <span data-ttu-id="93011-125">[Análise rápida](../../fast-parse.md) </span><span class="sxs-lookup"><span data-stu-id="93011-125">[Fast Parse](../../fast-parse.md) </span></span>  
 <span data-ttu-id="93011-126">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="93011-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="93011-127">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="93011-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
