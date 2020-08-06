---
title: Transformação Amostragem de Linhas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowsamplingtrans.f1
helpviewer_keywords:
- sampling seeds [Integration Services]
- random seeds
- random sampling
- sample data sets [Integration Services]
- Row Sampling transformation
- packages [Integration Services], samples
- datasets [Integration Services], sample
ms.assetid: b6caafd3-30b2-4368-82af-a44611d4cd39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c56f07d9fafa03752ef8c6572a13c6ad7c02a8c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686354"
---
# <a name="row-sampling-transformation"></a><span data-ttu-id="da89f-102">Transformação Amostragem de Linhas</span><span class="sxs-lookup"><span data-stu-id="da89f-102">Row Sampling Transformation</span></span>
  <span data-ttu-id="da89f-103">A transformação Amostragem de Linhas é usada para obter um subconjunto selecionado aleatoriamente de um conjunto de dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="da89f-103">The Row Sampling transformation is used to obtain a randomly selected subset of an input dataset.</span></span> <span data-ttu-id="da89f-104">Você pode especificar o tamanho exato da amostra de saída e especificar uma semente para o gerador de números aleatórios.</span><span class="sxs-lookup"><span data-stu-id="da89f-104">You can specify the exact size of the output sample, and specify a seed for the random number generator.</span></span>  
  
 <span data-ttu-id="da89f-105">Há muitos aplicativos para amostragem aleatória.</span><span class="sxs-lookup"><span data-stu-id="da89f-105">There are many applications for random sampling.</span></span> <span data-ttu-id="da89f-106">Por exemplo, uma empresa que deseje selecionar 50 empregados aleatoriamente para receber prêmios em uma loteria poderia usar a transformação Amostragem de Linhas no banco de dados de empregados para gerar o número exato de vencedores.</span><span class="sxs-lookup"><span data-stu-id="da89f-106">For example, a company that wanted to randomly select 50 employees to receive prizes in a lottery could use the Row Sampling transformation on the employee database to generate the exact number of winners.</span></span>  
  
 <span data-ttu-id="da89f-107">A transformação Amostragem de Linhas também é útil durante o desenvolvimento de pacote para criar um conjunto de dados pequeno, mas representativo.</span><span class="sxs-lookup"><span data-stu-id="da89f-107">The Row Sampling transformation is also useful during package development for creating a small but representative dataset.</span></span> <span data-ttu-id="da89f-108">Você pode testar a execução de pacote e transformação de dados com dados altamente representativos, porém mais rapidamente, porque uma amostra aleatória é usada em vez do conjunto de dados completo.</span><span class="sxs-lookup"><span data-stu-id="da89f-108">You can test package execution and data transformation with richly representative data, but more quickly because a random sample is used instead of the full dataset.</span></span> <span data-ttu-id="da89f-109">Como o conjunto de dados de exemplo usado pelo pacote de teste é sempre do mesmo tamanho, o uso do subconjunto de exemplos também facilita a identificação de problemas de desempenho no pacote.</span><span class="sxs-lookup"><span data-stu-id="da89f-109">Because the sample dataset used by the test package is always the same size, using the sample subset also makes it easier to identify performance problems in the package.</span></span>  
  
 <span data-ttu-id="da89f-110">Essa transformação é semelhante à transformação Amostragem Percentual, que cria um exemplo de conjunto dados selecionando uma porcentagem de linhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="da89f-110">This transformation is similar to the Percentage Sampling transformation, which creates a sample dataset by selecting a percentage of the input rows.</span></span> <span data-ttu-id="da89f-111">Consulte [Transformação Amostragem Percentual](percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="da89f-111">See [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span></span>  
  
## <a name="configuring-the-row-sampling-transformation"></a><span data-ttu-id="da89f-112">Configurando a transformação Amostragem de Linhas</span><span class="sxs-lookup"><span data-stu-id="da89f-112">Configuring the Row Sampling Transformation</span></span>  
 <span data-ttu-id="da89f-113">A transformação Amostragem de Linhas cria um exemplo de conjunto de dados selecionando um número especificado de linhas de entrada de transformação.</span><span class="sxs-lookup"><span data-stu-id="da89f-113">The Row Sampling transformation creates a sample dataset by selecting a specified number of the transformation input rows.</span></span> <span data-ttu-id="da89f-114">Como a seleção de linhas da entrada de transformação é aleatória, o exemplo resultante da entrada é representativo.</span><span class="sxs-lookup"><span data-stu-id="da89f-114">Because the selection of rows from the transformation input is random, the resultant sample is representative of the input.</span></span> <span data-ttu-id="da89f-115">Você também pode especificar a semente que será usada pelo gerador de números aleatórios para afetar a maneira como a transformação selecionará as linhas.</span><span class="sxs-lookup"><span data-stu-id="da89f-115">You can also specify the seed that is used by the random number generator, to affect how the transformation selects rows.</span></span>  
  
 <span data-ttu-id="da89f-116">O uso da mesma semente aleatória na mesma entrada de transformação sempre cria a mesma saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="da89f-116">Using the same random seed on the same transformation input always creates the same sample output.</span></span> <span data-ttu-id="da89f-117">Se nenhuma semente for especificada, a transformação usará a contagem de tiques do sistema operacional para criar o número aleatório.</span><span class="sxs-lookup"><span data-stu-id="da89f-117">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="da89f-118">Portanto, você poderia usar a mesma semente durante o teste para verificar os resultados da transformação durante o desenvolvimento e teste do pacote e, em seguida, alterar para uma semente aleatória quando o pacote for colocado em produção.</span><span class="sxs-lookup"><span data-stu-id="da89f-118">Therefore, you could use the same seed during testing, to verify the transformation results during the development and testing of the package, and then change to a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="da89f-119">A transformação Amostragem de Linhas inclui a propriedade personalizada `SamplingValue`.</span><span class="sxs-lookup"><span data-stu-id="da89f-119">The Row Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="da89f-120">Essa propriedade pode ser atualizada por uma expressão de propriedade quando o pacote é carregado.</span><span class="sxs-lookup"><span data-stu-id="da89f-120">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="da89f-121">Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Usar expressões de propriedade em pacotes](../../expressions/use-property-expressions-in-packages.md) e [Propriedades personalizadas da transformação](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="da89f-121">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="da89f-122">Essa transformação tem uma entrada e duas saídas.</span><span class="sxs-lookup"><span data-stu-id="da89f-122">This transformation has one input and two outputs.</span></span> <span data-ttu-id="da89f-123">Não tem nenhuma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="da89f-123">It has no error output.</span></span>  
  
 <span data-ttu-id="da89f-124">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="da89f-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="da89f-125">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Amostragem de Linha**, consulte [Editor de Transformação de Amostragem de Linha &#40;Página de Amostragem&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span><span class="sxs-lookup"><span data-stu-id="da89f-125">For more information about the properties that you can set in the **Row Sampling Transformation Editor** dialog box, see [Row Sampling Transformation Editor &#40;Sampling Page&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span></span>  
  
 <span data-ttu-id="da89f-126">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="da89f-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="da89f-127">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="da89f-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="da89f-128">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="da89f-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="da89f-129">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="da89f-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="da89f-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="da89f-130">Related Tasks</span></span>  
 [<span data-ttu-id="da89f-131">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="da89f-131">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
  
