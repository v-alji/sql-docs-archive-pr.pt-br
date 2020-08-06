---
title: Destino de treinamento do modelo de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e101a7e374f16b12b3a5aa30a49dbecd2632f06f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574834"
---
# <a name="data-mining-model-training-destination"></a><span data-ttu-id="3d816-102">Destino de treinamento do modelo de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="3d816-102">Data Mining Model Training Destination</span></span>
  <span data-ttu-id="3d816-103">Um destino de treinamento de modelos de mineração de dados treina modelos de mineração de dados ao passar os dados que o destino recebe pelos algoritmos de modelo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="3d816-103">The Data Mining Model Training destination trains data mining models by passing the data that the destination receives through the data mining model algorithms.</span></span> <span data-ttu-id="3d816-104">Vários modelos de mineração de dados poderão ser treinados por um destino se os modelos forem criados na mesma estrutura de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="3d816-104">Multiple data mining models can be trained by one destination if the models are built on the same data mining structure.</span></span> <span data-ttu-id="3d816-105">Para obter mais informações, consulte [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) e [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span><span class="sxs-lookup"><span data-stu-id="3d816-105">For more information, see [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) and [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span></span>  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a><span data-ttu-id="3d816-106">Configuração do destino Treinamento de Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="3d816-106">Configuration of the Data Mining Model Training Destination</span></span>  
 <span data-ttu-id="3d816-107">Se uma coluna de nível de caso da estrutura de destino e os modelos criados na estrutura tiverem o tipo de conteúdo KEY TIME ou KEY SEQUENCE, os dados de entrada deverão ser classificados nessa coluna.</span><span class="sxs-lookup"><span data-stu-id="3d816-107">If a case level column of the target structure and the models built on the structure has the content type KEY TIME or KEY SEQUENCE, the input data must be sorted on that column.</span></span> <span data-ttu-id="3d816-108">Por exemplo, os modelos criados pelo algoritmo do Microsoft Time Series utilizam o tipo de conteúdo KEY TIME.</span><span class="sxs-lookup"><span data-stu-id="3d816-108">For example, models built using the Microsoft Time Series algorithm use the content type KEY TIME.</span></span> <span data-ttu-id="3d816-109">Se os dados de entrada não forem classificados, o processamento do modelo poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="3d816-109">If input data is not sorted, the processing of the model may fail.</span></span> <span data-ttu-id="3d816-110">Se os dados exigirem a classificação, você poderá usar uma transformação do tipo Classificação antecipadamente no fluxo de dados para classificá-los.</span><span class="sxs-lookup"><span data-stu-id="3d816-110">If the data requires sorting, you can use a Sort transformation earlier in the data flow to sort the data.</span></span> <span data-ttu-id="3d816-111">Esse requisito não se aplica a colunas com o tipo de conteúdo KEY.</span><span class="sxs-lookup"><span data-stu-id="3d816-111">This requirement does not apply to columns with the KEY content type.</span></span> <span data-ttu-id="3d816-112">Para obter mais informações, consulte [Tipos de Conteúdo &#40; mineração de dados&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) e [Transformação Sort](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="3d816-112">For more information, see [Content Types &#40;Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) and [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3d816-113">A entrada para o destino Treinamento de Modelo de Mineração de Dados deve ser classificada.</span><span class="sxs-lookup"><span data-stu-id="3d816-113">The input to the Data Mining Model training destination must be sorted.</span></span> <span data-ttu-id="3d816-114">Para classificar os dados, você pode incluir um upstream de destino do tipo Classificação a partir do destino Treinamento de Modelo de Mineração de Dados no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="3d816-114">To sort the data, you can include a Sort destination upstream from the Data Mining Model Training destination in the data flow.</span></span> <span data-ttu-id="3d816-115">Para obter mais informações, consulte [Sort Transformation](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="3d816-115">For more information, see [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
 <span data-ttu-id="3d816-116">Este destino tem uma entrada e nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="3d816-116">This destination has one input and no output.</span></span>  
  
 <span data-ttu-id="3d816-117">O destino Treinamento do Modelo de Mineração de Dados usa um gerenciador de conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se conecta ao projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém a estrutura de mineração e os modelos de mineração treinados pelo destino.</span><span class="sxs-lookup"><span data-stu-id="3d816-117">The Data Mining Model Training destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models that the destination trains.</span></span> <span data-ttu-id="3d816-118">Para obter mais informações, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="3d816-118">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="3d816-119">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="3d816-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3d816-120">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Treinamento de Modelo de Mineração de Dados** , clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3d816-120">For more information about the properties that you can set in the **Data Mining Model Training Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3d816-121">Editor de Treinamento de Modelo de Mineração de Dados &#40;guia Conexão&#41;</span><span class="sxs-lookup"><span data-stu-id="3d816-121">Data Mining Model Training Editor &#40;Connection Tab&#41;</span></span>](../data-mining-model-training-editor-connection-tab.md)  
  
-   [<span data-ttu-id="3d816-122">Editor de Treinamento de Modelo de Mineração de Dados &#40;guia Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="3d816-122">Data Mining Model Training Editor &#40;Columns Tab&#41;</span></span>](../data-mining-model-training-editor-columns-tab.md)  
  
 <span data-ttu-id="3d816-123">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="3d816-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="3d816-124">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3d816-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3d816-125">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="3d816-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="3d816-126">Propriedades personalizadas do destino Treinamento do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="3d816-126">Data Mining Model Training Destination Custom Properties</span></span>](data-mining-model-training-destination-custom-properties.md)  
  
 <span data-ttu-id="3d816-127">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="3d816-127">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
