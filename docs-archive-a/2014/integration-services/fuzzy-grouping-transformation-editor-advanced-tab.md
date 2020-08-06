---
title: Editor de transformação Agrupamento Difuso (guia Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: dd820d75-b8a7-4515-aea4-3553ba5b442e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f5dd05eda56b4818914f659734eb3cdfb20c4d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571444"
---
# <a name="fuzzy-grouping-transformation-editor-advanced-tab"></a><span data-ttu-id="6985b-102">Editor de Transformação Agrupamento Difuso (guia Avançado)</span><span class="sxs-lookup"><span data-stu-id="6985b-102">Fuzzy Grouping Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="6985b-103">Use a guia **Avançado** da caixa de diálogo **Editor de Transformação Agrupamento Difuso** para especificar colunas de entrada e saída, definir limites de similaridade e definir delimitadores.</span><span class="sxs-lookup"><span data-stu-id="6985b-103">Use the **Advanced** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify input and output columns, set similarity thresholds, and define delimiters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6985b-104">As `Exhaustive` Propriedades e `MaxMemoryUsage` da transformação Agrupamento Difuso não estão disponíveis no **Editor de transformação Agrupamento Difuso**, mas podem ser definidas usando o **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="6985b-104">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Grouping transformation are not available in the **Fuzzy Grouping Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="6985b-105">Para obter mais informações sobre essas propriedades, consulte a seção Transformação Agrupamento Difuso em [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6985b-105">For more information on these properties, see the Fuzzy Grouping Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="6985b-106">Para saber mais sobre a transformação Agrupamento Difuso, consulte [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="6985b-106">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6985b-107">Opções</span><span class="sxs-lookup"><span data-stu-id="6985b-107">Options</span></span>  
 <span data-ttu-id="6985b-108">**Nome da coluna da chave de entrada**</span><span class="sxs-lookup"><span data-stu-id="6985b-108">**Input key column name**</span></span>  
 <span data-ttu-id="6985b-109">Especifique o nome de uma coluna de saída que contém o identificador exclusivo para cada coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="6985b-109">Specify the name of an output column that contains the unique identifier for each input row.</span></span> <span data-ttu-id="6985b-110">A coluna `_key_in` tem um valor que identifica exclusivamente cada linha.</span><span class="sxs-lookup"><span data-stu-id="6985b-110">The `_key_in` column has a value that uniquely identifies each row.</span></span>  
  
 <span data-ttu-id="6985b-111">**Nome da coluna da chave de saída**</span><span class="sxs-lookup"><span data-stu-id="6985b-111">**Output key column name**</span></span>  
 <span data-ttu-id="6985b-112">Especifique o nome de uma coluna de saída que contém um identificador exclusivo para a linha canônica de um grupo de linhas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="6985b-112">Specify the name of an output column that contains the unique identifier for the canonical row of a group of duplicate rows.</span></span> <span data-ttu-id="6985b-113">A coluna `_key_out` corresponde ao valor `_key_in` da linha de dados canônica.</span><span class="sxs-lookup"><span data-stu-id="6985b-113">The `_key_out` column corresponds to the `_key_in` value of the canonical data row.</span></span>  
  
 <span data-ttu-id="6985b-114">**Nome da coluna de pontuação de similaridade**</span><span class="sxs-lookup"><span data-stu-id="6985b-114">**Similarity score column name**</span></span>  
 <span data-ttu-id="6985b-115">Especifique um nome para a coluna que contém a pontuação de similaridade.</span><span class="sxs-lookup"><span data-stu-id="6985b-115">Specify a name for the column that contains the similarity score.</span></span> <span data-ttu-id="6985b-116">A pontuação de similaridade é um valor entre 0 e 1 que indica a similaridade da linha de entrada à linha canônica.</span><span class="sxs-lookup"><span data-stu-id="6985b-116">The similarity score is a value between 0 and 1 that indicates the similarity of the input row to the canonical row.</span></span> <span data-ttu-id="6985b-117">Quanto mais próxima de 1 for a pontuação, mais próxima será a correspondência da fila com a fila canônica.</span><span class="sxs-lookup"><span data-stu-id="6985b-117">The closer the score is to 1, the more closely the row matches the canonical row.</span></span>  
  
 <span data-ttu-id="6985b-118">**Limite de similaridade**</span><span class="sxs-lookup"><span data-stu-id="6985b-118">**Similarity threshold**</span></span>  
 <span data-ttu-id="6985b-119">Defina o limite de similaridade usando o controle deslizante.</span><span class="sxs-lookup"><span data-stu-id="6985b-119">Set the similarity threshold by using the slider.</span></span> <span data-ttu-id="6985b-120">Quanto mais próximo de 1 for o limite, mais linhas deverão ser similares umas às outras para se qualificarem como duplicatas.</span><span class="sxs-lookup"><span data-stu-id="6985b-120">The closer the threshold is to 1, the more the rows must resemble each other to qualify as duplicates.</span></span> <span data-ttu-id="6985b-121">Aumentar o limite pode melhorar a velocidade de correspondência, pois menos registros candidatos precisam ser considerados.</span><span class="sxs-lookup"><span data-stu-id="6985b-121">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="6985b-122">**Delimitadores de token**</span><span class="sxs-lookup"><span data-stu-id="6985b-122">**Token delimiters**</span></span>  
 <span data-ttu-id="6985b-123">A transformação fornece um conjunto padrão de delimitadores para criar tokens de dados, mas você pode adicionar ou remover delimitadores, conforme a necessidade, editando a lista.</span><span class="sxs-lookup"><span data-stu-id="6985b-123">The transformation provides a default set of delimiters for tokenizing data, but you can add or remove delimiters as needed by editing the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6985b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6985b-124">See Also</span></span>  
 <span data-ttu-id="6985b-125">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6985b-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="6985b-126">Identificar linhas de dados semelhantes por meio da transformação Agrupamento Difuso</span><span class="sxs-lookup"><span data-stu-id="6985b-126">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
