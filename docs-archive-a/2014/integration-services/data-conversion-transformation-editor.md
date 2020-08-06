---
title: Editor de transformação conversão de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontransformation.f1
helpviewer_keywords:
- Data Conversion Transformation Editor
ms.assetid: 7b4e4873-e8fe-4549-a965-65bebdb270bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4b893f04dcca2dd2a1a5874b55c1c1c608aaeb12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685883"
---
# <a name="data-conversion-transformation-editor"></a><span data-ttu-id="bfef2-102">Editor de Transformação Conversão de Dados</span><span class="sxs-lookup"><span data-stu-id="bfef2-102">Data Conversion Transformation Editor</span></span>
  <span data-ttu-id="bfef2-103">Use a caixa de diálogo **Editor de Transformação Conversão de Dados** para selecionar as colunas a converter, selecionar o tipo de dados ao qual converter a coluna e definir atributos de conversão.</span><span class="sxs-lookup"><span data-stu-id="bfef2-103">Use the **Data Conversion Transformation Editor** dialog box to select the columns to convert, select the data type to which the column is converted, and set conversion attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bfef2-104">A `FastParse` propriedade das colunas de saída da transformação conversão de dados não está disponível no **Editor de transformação conversão de dados**, mas pode ser definida usando o **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="bfef2-104">The `FastParse` property of the output columns of the Data Conversion transformation is not available in the **Data Conversion Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="bfef2-105">Para obter mais informações sobre essa propriedade, consulte a seção Transformação Conversão de Dados em [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bfef2-105">For more information on this property, see the Data Conversion Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="bfef2-106">Para saber mais sobre a transformação Conversão de Dados, consulte [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="bfef2-106">To learn more about the Data Conversion transformation, see [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bfef2-107">Opções</span><span class="sxs-lookup"><span data-stu-id="bfef2-107">Options</span></span>  
 <span data-ttu-id="bfef2-108">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="bfef2-108">**Available Input Columns**</span></span>  
 <span data-ttu-id="bfef2-109">Selecione as colunas a converter, utilizando as caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="bfef2-109">Select columns to convert by using the check boxes.</span></span> <span data-ttu-id="bfef2-110">as seleções adicionam colunas de entrada à tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="bfef2-110">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="bfef2-111">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="bfef2-111">**Input Column**</span></span>  
 <span data-ttu-id="bfef2-112">Selecione colunas a converter na lista de colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bfef2-112">Select columns to convert from the list of available input columns.</span></span> <span data-ttu-id="bfef2-113">Suas seleções serão refletidas nas caixas de seleção marcadas acima.</span><span class="sxs-lookup"><span data-stu-id="bfef2-113">Your selections are reflected in the check box selections above.</span></span>  
  
 <span data-ttu-id="bfef2-114">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="bfef2-114">**Output Alias**</span></span>  
 <span data-ttu-id="bfef2-115">Digite um alias para cada coluna nova.</span><span class="sxs-lookup"><span data-stu-id="bfef2-115">Type an alias for each new column.</span></span> <span data-ttu-id="bfef2-116">O padrão é `Copy of` seguido do nome da coluna de entrada; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="bfef2-116">The default is `Copy of` followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="bfef2-117">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="bfef2-117">**Data Type**</span></span>  
 <span data-ttu-id="bfef2-118">Selecione na lista um tipo de dados disponível.</span><span class="sxs-lookup"><span data-stu-id="bfef2-118">Select an available data type from the list.</span></span> <span data-ttu-id="bfef2-119">Para obter mais informações, consulte [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="bfef2-119">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="bfef2-120">**Comprimento**</span><span class="sxs-lookup"><span data-stu-id="bfef2-120">**Length**</span></span>  
 <span data-ttu-id="bfef2-121">Defina o tamanho de coluna para dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bfef2-121">Set the column length for string data.</span></span>  
  
 <span data-ttu-id="bfef2-122">**Precisão**</span><span class="sxs-lookup"><span data-stu-id="bfef2-122">**Precision**</span></span>  
 <span data-ttu-id="bfef2-123">Defina a precisão para dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="bfef2-123">Set the precision for numeric data.</span></span>  
  
 <span data-ttu-id="bfef2-124">**Escala**</span><span class="sxs-lookup"><span data-stu-id="bfef2-124">**Scale**</span></span>  
 <span data-ttu-id="bfef2-125">Defina a escala para dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="bfef2-125">Set the scale for numeric data.</span></span>  
  
 <span data-ttu-id="bfef2-126">**Página de código**</span><span class="sxs-lookup"><span data-stu-id="bfef2-126">**Code page**</span></span>  
 <span data-ttu-id="bfef2-127">Selecione a página de código apropriada para colunas de tipo DT_STR.</span><span class="sxs-lookup"><span data-stu-id="bfef2-127">Select the appropriate code page for columns of type DT_STR.</span></span>  
  
 <span data-ttu-id="bfef2-128">**Configurar saída de erro**</span><span class="sxs-lookup"><span data-stu-id="bfef2-128">**Configure error output**</span></span>  
 <span data-ttu-id="bfef2-129">Especifique como tratar erros de nível de linha usando a caixa de diálogo [Configurar Saída de Erro](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="bfef2-129">Specify how to handle row-level errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfef2-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bfef2-130">See Also</span></span>  
 <span data-ttu-id="bfef2-131">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bfef2-131">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="bfef2-132">Converter dados em um tipo de dados diferente por meio da transformação Conversão de Dados</span><span class="sxs-lookup"><span data-stu-id="bfef2-132">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>](data-flow/transformations/convert-data-type-by-using-data-conversion-transformation.md)  
  
  
