---
title: Transformação Amostragem Percentual | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtrans.f1
helpviewer_keywords:
- testing mining models
- sampling seeds [Integration Services]
- data mining [Analysis Services], sample data sets
- Percentage Sampling transformation
- sample data sets [Integration Services]
- datasets [Integration Services], sample
- training mining models
ms.assetid: 59767e52-f732-4b3f-8602-be50d0a64ef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e5fe41ecf4a2ca0f9d20eec2c8e10af8ed4cd47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686357"
---
# <a name="percentage-sampling-transformation"></a><span data-ttu-id="a7b4d-102">transformação Amostragem Percentual</span><span class="sxs-lookup"><span data-stu-id="a7b4d-102">Percentage Sampling Transformation</span></span>
  <span data-ttu-id="a7b4d-103">A transformação Amostragem Percentual cria um conjunto de dados de exemplo, selecionando um percentual das linhas de entrada da transformação.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-103">The Percentage Sampling transformation creates a sample data set by selecting a percentage of the transformation input rows.</span></span> <span data-ttu-id="a7b4d-104">O conjunto de dados de exemplo é uma seleção aleatória das linhas da entrada da transformação, para que o exemplo resultante seja representativo da entrada.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-104">The sample data set is a random selection of rows from the transformation input, to make the resultant sample representative of the input.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7b4d-105">Além do percentual especificado, a transformação Amostragem Percentual utiliza um algoritmo para determinar se uma linha pode ser incluída na saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-105">In addition to the specified percentage, the Percentage Sampling transformation uses an algorithm to determine whether a row should be included in the sample output.</span></span> <span data-ttu-id="a7b4d-106">Isso significa que o número de linhas na saída de exemplo pode não refletir exatamente o percentual especificado.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-106">This means that the number of rows in the sample output may not exactly reflect the specified percentage.</span></span> <span data-ttu-id="a7b4d-107">Por exemplo, ao especificar 10% para um conjunto de dados de entrada com 25.000 linhas, é possível que não seja possível gerar uma amostra com 2.500 linhas. A amostra pode ter algumas linhas a menos ou a mais.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-107">For example, specifying 10 percent for an input data set that has 25,000 rows may not generate a sample with 2,500 rows; the sample may have a few more or a few less rows.</span></span>  
  
 <span data-ttu-id="a7b4d-108">A transformação Amostragem Percentual é particularmente útil para mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-108">The Percentage Sampling transformation is especially useful for data mining.</span></span> <span data-ttu-id="a7b4d-109">Utilizando-se essa transformação, você pode dividir aleatoriamente um conjunto de dados em dois: um para treinar o modelo de mineração de dados e o outro para testá-lo.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-109">By using this transformation, you can randomly divide a data set into two data sets: one for training the data mining model, and one for testing the model.</span></span>  
  
 <span data-ttu-id="a7b4d-110">A transformação Amostragem Percentual também é útil para criar conjuntos de dados de exemplo para desenvolvimento de pacote.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-110">The Percentage Sampling transformation is also useful for creating sample data sets for package development.</span></span> <span data-ttu-id="a7b4d-111">Aplicando-se a transformação Amostragem Percentual a um fluxo de dados, você pode reduzir de modo uniforme o tamanho do conjunto de dados, preservando as características de seus dados.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-111">By applying the Percentage Sampling transformation to a data flow, you can uniformly reduce the size of the data set while preserving its data characteristics.</span></span> <span data-ttu-id="a7b4d-112">O pacote de teste pode ser então executado mais rapidamente, pois ele usa um conjunto de dados pequeno, porém representativo.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-112">The test package can then run more quickly because it uses a small, but representative, data set.</span></span>  
  
## <a name="configuration-the-percentage-sampling-transformation"></a><span data-ttu-id="a7b4d-113">Configuração da transformação Amostragem Percentual</span><span class="sxs-lookup"><span data-stu-id="a7b4d-113">Configuration the Percentage Sampling Transformation</span></span>  
 <span data-ttu-id="a7b4d-114">Você pode especificar uma amostragem da semente para modificar o comportamento do gerador de números aleatórios que a transformação utiliza para selecionar linhas.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-114">You can specify a sampling seed to modify the behavior of the random number generator that the transformation uses to select rows.</span></span> <span data-ttu-id="a7b4d-115">Se a mesma amostragem da semente for utilizada, a transformação sempre criará a mesma saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-115">If the same sampling seed is used, the transformation always creates the same sample output.</span></span> <span data-ttu-id="a7b4d-116">Se nenhuma semente for especificada, a transformação usará a contagem de tiques do sistema operacional para criar o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-116">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="a7b4d-117">Portanto, você pode optar por utilizar uma semente padrão quando quiser verificar os resultados da transformação durante o desenvolvimento e teste de um pacote e, em seguida, fazer a alteração para utilizar uma semente aleatória quando o pacote for colocado em produção.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-117">Therefore, you might choose to use a standard seed when you want to verify the transformation results during the development and testing of a package, and then change to use a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="a7b4d-118">Essa transformação é semelhante à transformação Amostragem de Linhas, que cria um conjunto dados de exemplo, selecionando um número especificado de linhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-118">This transformation is similar to the Row Sampling transformation, which creates a sample data set by selecting a specified number of the input rows.</span></span> <span data-ttu-id="a7b4d-119">Para obter mais informações, consulte [Row Sampling Transformation](row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a7b4d-119">For more information, see [Row Sampling Transformation](row-sampling-transformation.md).</span></span>  
  
 <span data-ttu-id="a7b4d-120">A transformação Amostragem Percentual inclui a propriedade personalizada `SamplingValue`.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-120">The Percentage Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="a7b4d-121">Essa propriedade pode ser atualizada por uma expressão de propriedade quando o pacote é carregado.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="a7b4d-122">Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Usar expressões de propriedade em pacotes](../../expressions/use-property-expressions-in-packages.md) e [Propriedades personalizadas da transformação](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a7b4d-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="a7b4d-123">A transformação tem uma entrada e duas saídas.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-123">The transformation has one input and two outputs.</span></span> <span data-ttu-id="a7b4d-124">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-124">It does not support an error output.</span></span>  
  
 <span data-ttu-id="a7b4d-125">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-125">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a7b4d-126">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Amostragem Percentual** , consulte [Percentage Sampling Transformation Editor](../../percentage-sampling-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a7b4d-126">For more information about the properties that you can set in the **Percentage Sampling Transformation Editor** dialog box, see [Percentage Sampling Transformation Editor](../../percentage-sampling-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="a7b4d-127">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7b4d-127">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="a7b4d-128">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a7b4d-128">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a7b4d-129">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="a7b4d-129">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="a7b4d-130">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="a7b4d-130">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="a7b4d-131">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a7b4d-131">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
