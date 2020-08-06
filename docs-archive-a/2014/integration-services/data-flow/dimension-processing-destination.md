---
title: Destino de processamento de dimensões | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimensionprocessingdest.f1
helpviewer_keywords:
- Dimension Processing destination
- loading dimensions
- destinations [Integration Services], Dimension Processing
- dimensions [Analysis Services], processing
ms.assetid: 4c49bb95-7259-42f4-a785-bb6aaf5f8566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61cde87ac4fa5fcb1352491d787674447dd404b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571496"
---
# <a name="dimension-processing-destination"></a><span data-ttu-id="90643-102">Destino de processamento de dimensões</span><span class="sxs-lookup"><span data-stu-id="90643-102">Dimension Processing Destination</span></span>
  <span data-ttu-id="90643-103">O destino de Processamento de Dimensões carrega e processa uma dimensão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90643-103">The Dimension Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimension.</span></span> <span data-ttu-id="90643-104">Para obter mais informações sobre dimensões, consulte [Dimensões &#40;Analysis Services – Dados Multidimensionais&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="90643-104">For more information about dimensions, see [Dimensions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="90643-105">O Destino de Processamento de Dimensões inclui os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="90643-105">The Dimension Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="90643-106">Opções para executar o processamento incremental, completo ou atualizado.</span><span class="sxs-lookup"><span data-stu-id="90643-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="90643-107">Configuração de erro, para especificar se o processamento de dimensões ignora erros ou é interrompido depois de um determinado número de erros.</span><span class="sxs-lookup"><span data-stu-id="90643-107">Error configuration, to specify whether dimension processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="90643-108">Mapeamento de colunas de entrada para colunas nas tabelas de dimensão.</span><span class="sxs-lookup"><span data-stu-id="90643-108">Mapping of input columns to columns in dimension tables.</span></span>  
  
 <span data-ttu-id="90643-109">Para obter mais informações sobre processamento de objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consulte [Opções e configurações de processamento &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="90643-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
## <a name="configuration-of-the-dimension-processing-destination"></a><span data-ttu-id="90643-110">Configuração do o destino Processamento de Dimensão</span><span class="sxs-lookup"><span data-stu-id="90643-110">Configuration of the Dimension Processing Destination</span></span>  
 <span data-ttu-id="90643-111">O Destino de Processamento de Dimensões usa um gerenciador de conexões do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para se conectar ao projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém as dimensões processadas pelo destino.</span><span class="sxs-lookup"><span data-stu-id="90643-111">The Dimension Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the dimensions the destination processes.</span></span> <span data-ttu-id="90643-112">Para obter mais informações, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="90643-112">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="90643-113">Esse destino tem uma entrada.</span><span class="sxs-lookup"><span data-stu-id="90643-113">This destination has one input.</span></span> <span data-ttu-id="90643-114">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="90643-114">It does not support an error output.</span></span>  
  
 <span data-ttu-id="90643-115">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="90643-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="90643-116">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Destino de Processamento de Dimensões** , clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="90643-116">For more information about the properties that you can set in the **Dimension Processing Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="90643-117">Editor de Destino de Processamento de Dimensões &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="90643-117">Dimension Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../dimension-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="90643-118">Editor de Destino de Processamento de Dimensões &#40;página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="90643-118">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../dimension-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="90643-119">Editor de Destino de Processamento de Dimensões &#40;Página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="90643-119">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../dimension-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="90643-120">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="90643-120">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="90643-121">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="90643-121">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="90643-122">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="90643-122">Common Properties</span></span>](../common-properties.md)  
  
 <span data-ttu-id="90643-123">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="90643-123">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90643-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90643-124">See Also</span></span>  
 <span data-ttu-id="90643-125">[Fluxo de Dados](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="90643-125">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="90643-126">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="90643-126">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
