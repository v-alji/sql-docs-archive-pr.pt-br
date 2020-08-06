---
title: Editor de transformação Agrupamento Difuso (guia colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.columns.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 24f4539f-2a9f-4acd-acc7-06228a07f7df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d3aef9c30a81760b7f09378a8ecd66fee0dac62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679430"
---
# <a name="fuzzy-grouping-transformation-editor-columns-tab"></a><span data-ttu-id="c7c97-102">Editor de Transformação Agrupamento Difuso (guia Colunas)</span><span class="sxs-lookup"><span data-stu-id="c7c97-102">Fuzzy Grouping Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="c7c97-103">Use a guia **Colunas** da caixa de diálogo **Editor de Transformação Agrupamento Difuso** para especificar as colunas usadas para agrupar linhas com valores duplicados.</span><span class="sxs-lookup"><span data-stu-id="c7c97-103">Use the **Columns** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify the columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="c7c97-104">Para saber mais sobre a transformação Agrupamento Difuso, consulte [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c7c97-104">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c7c97-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c7c97-105">Options</span></span>  
 <span data-ttu-id="c7c97-106">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="c7c97-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="c7c97-107">Selecione nesta lista as colunas de entrada usadas para agrupar linhas com valores duplicados.</span><span class="sxs-lookup"><span data-stu-id="c7c97-107">Select from this list the input columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="c7c97-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c7c97-108">**Name**</span></span>  
 <span data-ttu-id="c7c97-109">Visualize os nomes das colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c7c97-109">View the names of available input columns.</span></span>  
  
 <span data-ttu-id="c7c97-110">**Passagem**</span><span class="sxs-lookup"><span data-stu-id="c7c97-110">**Pass Through**</span></span>  
 <span data-ttu-id="c7c97-111">Selecione se a coluna de entrada deve ser incluída na saída da transformação.</span><span class="sxs-lookup"><span data-stu-id="c7c97-111">Select whether to include the input column in the output of the transformation.</span></span> <span data-ttu-id="c7c97-112">Todas as colunas usadas para agrupar são copiadas automaticamente para a saída.</span><span class="sxs-lookup"><span data-stu-id="c7c97-112">All columns used for grouping are automatically copied to the output.</span></span> <span data-ttu-id="c7c97-113">Você pode incluir colunas adicionais, marcando esta coluna.</span><span class="sxs-lookup"><span data-stu-id="c7c97-113">You can include additional columns by checking this column.</span></span>  
  
 <span data-ttu-id="c7c97-114">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="c7c97-114">**Input Column**</span></span>  
 <span data-ttu-id="c7c97-115">Selecione uma das colunas de entrada selecionadas anteriormente na lista **Colunas de Entrada Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="c7c97-115">Select one of the input columns selected earlier in the **Available Input Columns** list.</span></span>  
  
 <span data-ttu-id="c7c97-116">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="c7c97-116">**Output Alias**</span></span>  
 <span data-ttu-id="c7c97-117">Digite um nome descritivo para a coluna de saída correspondente.</span><span class="sxs-lookup"><span data-stu-id="c7c97-117">Enter a descriptive name for the corresponding output column.</span></span> <span data-ttu-id="c7c97-118">Por padrão, o nome da coluna de saída é idêntico ao nome da coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="c7c97-118">By default, the output column name is the same as the input column name.</span></span>  
  
 <span data-ttu-id="c7c97-119">**Alias de Saída de Grupo**</span><span class="sxs-lookup"><span data-stu-id="c7c97-119">**Group Output Alias**</span></span>  
 <span data-ttu-id="c7c97-120">Digite um nome descritivo para a coluna que conterá o valor canônico para as duplicatas agrupadas.</span><span class="sxs-lookup"><span data-stu-id="c7c97-120">Enter a descriptive name for the column that will contain the canonical value for the grouped duplicates.</span></span> <span data-ttu-id="c7c97-121">O nome padrão dessa coluna de saída é o nome da coluna de entrada acrescido de _clean.</span><span class="sxs-lookup"><span data-stu-id="c7c97-121">The default name of this output column is the input column name with _clean appended.</span></span>  
  
 <span data-ttu-id="c7c97-122">**Associar Tipo**</span><span class="sxs-lookup"><span data-stu-id="c7c97-122">**Match Type**</span></span>  
 <span data-ttu-id="c7c97-123">Selecione correspondência difusa ou exata.</span><span class="sxs-lookup"><span data-stu-id="c7c97-123">Select fuzzy or exact matching.</span></span> <span data-ttu-id="c7c97-124">As linhas serão consideradas duplicatas se forem suficientemente semelhantes em todas as colunas que têm tipo de correspondência difusa.</span><span class="sxs-lookup"><span data-stu-id="c7c97-124">Rows are considered duplicates if they are sufficiently similar across all columns with a fuzzy match type.</span></span> <span data-ttu-id="c7c97-125">Se você também especificar correspondência exata em certas colunas, apenas as linhas que contiverem valores idênticos nessas colunas serão consideradas possíveis duplicatas.</span><span class="sxs-lookup"><span data-stu-id="c7c97-125">If you also specify exact matching on certain columns, only rows that contain identical values in the exact matching columns are considered as possible duplicates.</span></span> <span data-ttu-id="c7c97-126">Portanto, se souber que certa coluna não contém nenhum erro ou inconsistência, você poderá especificar correspondência exata nessa coluna para aumentar a exatidão da correspondência difusa nas outras colunas.</span><span class="sxs-lookup"><span data-stu-id="c7c97-126">Therefore, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column to increase the accuracy of the fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="c7c97-127">**Similaridade Mínima**</span><span class="sxs-lookup"><span data-stu-id="c7c97-127">**Minimum Similarity**</span></span>  
 <span data-ttu-id="c7c97-128">Defina o limite de similaridade no nível de junção, usando o controle deslizante.</span><span class="sxs-lookup"><span data-stu-id="c7c97-128">Set the similarity threshold at the join level by using the slider.</span></span> <span data-ttu-id="c7c97-129">Quanto mais próximo de 1 for o valor, maior deverá ser a semelhança entre o valor de pesquisa e o valor da origem para a qualificação de correspondências.</span><span class="sxs-lookup"><span data-stu-id="c7c97-129">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="c7c97-130">Aumentar o limite pode melhorar a velocidade de correspondência, já que menos registros serão considerados candidatos.</span><span class="sxs-lookup"><span data-stu-id="c7c97-130">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="c7c97-131">**Alias de Saída de Similaridade**</span><span class="sxs-lookup"><span data-stu-id="c7c97-131">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="c7c97-132">Especifique o nome da nova coluna de saída que conterá as pontuações de similaridade da junção selecionada.</span><span class="sxs-lookup"><span data-stu-id="c7c97-132">Specify the name for a new output column that contains the similarity scores for the selected join.</span></span> <span data-ttu-id="c7c97-133">Se você deixar este valor vazio, a coluna de saída não será criada.</span><span class="sxs-lookup"><span data-stu-id="c7c97-133">If you leave this value empty, the output column is not created.</span></span>  
  
 <span data-ttu-id="c7c97-134">**Numerais**</span><span class="sxs-lookup"><span data-stu-id="c7c97-134">**Numerals**</span></span>  
 <span data-ttu-id="c7c97-135">Especifique a significância dos numerais à esquerda e à direita na comparação dos dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="c7c97-135">Specify the significance of leading and trailing numerals in comparing the column data.</span></span> <span data-ttu-id="c7c97-136">Por exemplo, se os numerais à esquerda forem significativos, "123 Main Street" não será grupado com "456 Main Street".</span><span class="sxs-lookup"><span data-stu-id="c7c97-136">For example, if leading numerals are significant, "123 Main Street" will not be grouped with "456 Main Street."</span></span>  
  
|<span data-ttu-id="c7c97-137">Valor</span><span class="sxs-lookup"><span data-stu-id="c7c97-137">Value</span></span>|<span data-ttu-id="c7c97-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7c97-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c7c97-139">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="c7c97-139">**Neither**</span></span>|<span data-ttu-id="c7c97-140">Numerais à esquerda e à direita não são significativos.</span><span class="sxs-lookup"><span data-stu-id="c7c97-140">Leading and trailing numerals are not significant.</span></span>|  
|<span data-ttu-id="c7c97-141">**Conceitua**</span><span class="sxs-lookup"><span data-stu-id="c7c97-141">**Leading**</span></span>|<span data-ttu-id="c7c97-142">Apenas numerais à esquerda são significativos.</span><span class="sxs-lookup"><span data-stu-id="c7c97-142">Only leading numerals are significant.</span></span>|  
|<span data-ttu-id="c7c97-143">**À Direita**</span><span class="sxs-lookup"><span data-stu-id="c7c97-143">**Trailing**</span></span>|<span data-ttu-id="c7c97-144">Apenas numerais à direita são significativos.</span><span class="sxs-lookup"><span data-stu-id="c7c97-144">Only trailing numerals are significant.</span></span>|  
|<span data-ttu-id="c7c97-145">**À Esquerda e À Direita**</span><span class="sxs-lookup"><span data-stu-id="c7c97-145">**LeadingAndTrailing**</span></span>|<span data-ttu-id="c7c97-146">Numerais tanto à esquerda, quanto à direita são significativos.</span><span class="sxs-lookup"><span data-stu-id="c7c97-146">Both leading and trailing numerals are significant.</span></span>|  
  
 <span data-ttu-id="c7c97-147">**Sinalizadores de Comparação**</span><span class="sxs-lookup"><span data-stu-id="c7c97-147">**Comparison Flags**</span></span>  
 <span data-ttu-id="c7c97-148">Para obter mais informações sobre as opções de comparação de cadeias de caracteres, consulte [Comparando dados de cadeia de caracteres](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="c7c97-148">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c97-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7c97-149">See Also</span></span>  
 <span data-ttu-id="c7c97-150">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c7c97-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="c7c97-151">Identificar linhas de dados semelhantes por meio da transformação Agrupamento Difuso</span><span class="sxs-lookup"><span data-stu-id="c7c97-151">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
