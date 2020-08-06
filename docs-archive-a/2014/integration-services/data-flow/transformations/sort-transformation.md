---
title: Transformação Classificação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttrans.f1
helpviewer_keywords:
- Sort transformation
- descending sorts
- ascending sorts
- sorting data [Integration Services]
- multiple sorts
- duplicate data [Integration Services]
ms.assetid: 728c9351-84a8-4a89-be4d-d50d4adc04e0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7039d02b6cc55355c3b27e5694474df4666570ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575236"
---
# <a name="sort-transformation"></a><span data-ttu-id="92318-102">Transformação Classificação</span><span class="sxs-lookup"><span data-stu-id="92318-102">Sort Transformation</span></span>
  <span data-ttu-id="92318-103">A transformação Classificação ordena os dados de entrada de modo crescente ou decrescente e os copia na saída da transformação.</span><span class="sxs-lookup"><span data-stu-id="92318-103">The Sort transformation sorts input data in ascending or descending order and copies the sorted data to the transformation output.</span></span> <span data-ttu-id="92318-104">Você pode aplicar várias classificações a uma entrada. Cada classificação é identificada por um numeral que determina a ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="92318-104">You can apply multiple sorts to an input; each sort is identified by a numeral that determines the sort order.</span></span> <span data-ttu-id="92318-105">A coluna com o número mais baixo é classificada primeiro, a com o segundo número mais baixo é classificada em seguida e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="92318-105">The column with the lowest number is sorted first, the sort column with the second lowest number is sorted next, and so on.</span></span> <span data-ttu-id="92318-106">Por exemplo, se uma coluna denominada **CountryRegion** tiver uma ordem de classificação 1 e uma coluna denominada **City** tiver uma ordem de classificação 2, a saída será ordenada por país/região e depois por cidade.</span><span class="sxs-lookup"><span data-stu-id="92318-106">For example, if a column named **CountryRegion** has a sort order of 1 and a column named **City** has a sort order of 2, the output is sorted by country/region and then by city.</span></span> <span data-ttu-id="92318-107">Um número positivo indica que a classificação está aumentando, e um negativo que está diminuindo.</span><span class="sxs-lookup"><span data-stu-id="92318-107">A positive number denotes that the sort is ascending, and a negative number denotes that the sort is descending.</span></span> <span data-ttu-id="92318-108">As colunas que não forem classificadas terão a ordem de classificação 0.</span><span class="sxs-lookup"><span data-stu-id="92318-108">Columns that are not sorted have a sort order of 0.</span></span> <span data-ttu-id="92318-109">As colunas que não forem selecionadas para classificação serão automaticamente copiadas para a saída de transformação junto com as colunas classificadas.</span><span class="sxs-lookup"><span data-stu-id="92318-109">Columns that are not selected for sorting are automatically copied to the transformation output together with the sorted columns.</span></span>  
  
 <span data-ttu-id="92318-110">A transformação Classificação inclui um conjunto de opções de comparação para definir como a transformação controla os dados de cadeia de caracteres em uma coluna.</span><span class="sxs-lookup"><span data-stu-id="92318-110">The Sort transformation includes a set of comparison options to define how the transformation handles the string data in a column.</span></span> <span data-ttu-id="92318-111">Para obter mais informações, consulte [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="92318-111">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92318-112">A transformação Classificação não ordena os GUIDs na mesma ordem como a cláusula ORDER BY faz em Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="92318-112">The Sort transformation does not sort GUIDs in the same order as the ORDER BY clause does in Transact-SQL.</span></span> <span data-ttu-id="92318-113">Enquanto a transformação Classificação ordena os GUIDs que iniciam com 0-9 antes dos GUIDs que iniciam com A-F, a cláusula ORDER BY, como implementado no [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], faz a classificação de modo diferente.</span><span class="sxs-lookup"><span data-stu-id="92318-113">While the Sort transformation sorts GUIDs that start with 0-9 before GUIDs that start with A-F, the ORDER BY clause, as implemented in the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], sorts them differently.</span></span> <span data-ttu-id="92318-114">Para obter mais informações, consulte [Cláusula ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92318-114">For more information, see [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="92318-115">A transformação Classificação também pode remover linhas duplicadas como parte de sua classificação.</span><span class="sxs-lookup"><span data-stu-id="92318-115">The Sort transformation can also remove duplicate rows as part of its sort.</span></span> <span data-ttu-id="92318-116">Linhas duplicadas são linhas com os mesmos valores da chave de classificação.</span><span class="sxs-lookup"><span data-stu-id="92318-116">Duplicate rows are rows with the same sort key values.</span></span> <span data-ttu-id="92318-117">O valor da chave de classificação é gerado com base nas opções de comparação da cadeia de caracteres que estiverem sendo usadas. Isto significa que cadeias de caracteres literais diferentes podem ter os mesmos valores da chave de classificação.</span><span class="sxs-lookup"><span data-stu-id="92318-117">The sort key value is generated based on the string comparison options being used, which means that different literal strings may have the same sort key values.</span></span> <span data-ttu-id="92318-118">A transformação identifica como duplicidade as linhas nas colunas de entrada que têm valores diferentes porém a mesma chave de classificação.</span><span class="sxs-lookup"><span data-stu-id="92318-118">The transformation identifies rows in the input columns that have different values but the same sort key as duplicates.</span></span>  
  
 <span data-ttu-id="92318-119">A transformação Classificação inclui a propriedade personalizada `MaximumThreads` que pode ser atualizada por uma expressão de propriedade quando o pacote for carregado.</span><span class="sxs-lookup"><span data-stu-id="92318-119">The Sort transformation includes the `MaximumThreads` custom property that can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="92318-120">Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Usar expressões de propriedade em pacotes](../../expressions/use-property-expressions-in-packages.md) e [Propriedades personalizadas da transformação](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="92318-120">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="92318-121">Essa transformação tem uma entrada e uma saída.</span><span class="sxs-lookup"><span data-stu-id="92318-121">This transformation has one input and one output.</span></span> <span data-ttu-id="92318-122">Ela não oferece suporte a saídas de erro.</span><span class="sxs-lookup"><span data-stu-id="92318-122">It does not support error outputs.</span></span>  
  
## <a name="configuration-of-the-sort-transformation"></a><span data-ttu-id="92318-123">Configuração da transformação Classificação</span><span class="sxs-lookup"><span data-stu-id="92318-123">Configuration of the Sort Transformation</span></span>  
 <span data-ttu-id="92318-124">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="92318-124">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="92318-125">Para obter informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Classificação** , consulte [Sort Transformation Editor](../../sort-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="92318-125">For information about the properties that you can set in the **Sort Transformation Editor** dialog box, see [Sort Transformation Editor](../../sort-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="92318-126">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="92318-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="92318-127">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="92318-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="92318-128">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="92318-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="92318-129">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="92318-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="92318-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="92318-130">Related Tasks</span></span>  
 <span data-ttu-id="92318-131">Para obter mais informações sobre como definir as propriedades do componente, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="92318-131">For more information about how to set properties of the component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="92318-132">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="92318-132">Related Content</span></span>  
 <span data-ttu-id="92318-133">Exemplo, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), em codeplex.com.</span><span class="sxs-lookup"><span data-stu-id="92318-133">Sample, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), on codeplex.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92318-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92318-134">See Also</span></span>  
 <span data-ttu-id="92318-135">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="92318-135">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="92318-136">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="92318-136">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
