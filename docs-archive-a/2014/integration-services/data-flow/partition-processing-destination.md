---
title: Destino de processamento de partições | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partitionprocessingdest.f1
helpviewer_keywords:
- partitions [Analysis Services], processing
- Partition Processing destination [Integration Services]
- destinations [Integration Services], Partition Processing
ms.assetid: 36c592ff-3f78-4a58-b496-31c1c8eee131
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d32306328f7a0575e55397d5209b4767d0cf1bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571476"
---
# <a name="partition-processing-destination"></a><span data-ttu-id="6c9b0-102">Destino de processamento de partições</span><span class="sxs-lookup"><span data-stu-id="6c9b0-102">Partition Processing Destination</span></span>
  <span data-ttu-id="6c9b0-103">O destino de Processamento de Partição carrega e processa uma partição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c9b0-103">The Partition Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partition.</span></span> <span data-ttu-id="6c9b0-104">Para obter mais informações sobre partições, consulte [Partições &#40;Analysis Services – Dados Multidimensionais&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="6c9b0-104">For more information about partitions, see [Partitions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="6c9b0-105">O destino de Processamento de Partições inclui os seguintes recursos :</span><span class="sxs-lookup"><span data-stu-id="6c9b0-105">The Partition Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="6c9b0-106">Opções para executar o processamento incremental, completo ou atualizado.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="6c9b0-107">Configuração de erro, para especificar se o processamento ignora erros ou é interrompido depois de um número especificado de erros.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-107">Error configuration, to specify whether processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="6c9b0-108">Mapeamento das colunas de entrada em colunas de partição.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-108">Mapping of input columns to partition columns.</span></span>  
  
 <span data-ttu-id="6c9b0-109">Para obter mais informações sobre processamento de objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consulte [Opções e configurações de processamento &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="6c9b0-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c9b0-110">As tarefas descritas aqui não se aplicam a modelos de tabela do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-110">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="6c9b0-111">Você não pode mapear colunas de entrada para as colunas de partição em modelos de tabela.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-111">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="6c9b0-112">Você pode usar a tarefa Executar DDL do Analysis Services [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) para processar a partição.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-112">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="configuration-of-the-partition-processing-destination"></a><span data-ttu-id="6c9b0-113">Configuração do destino do processamento da partição</span><span class="sxs-lookup"><span data-stu-id="6c9b0-113">Configuration of the Partition Processing Destination</span></span>  
 <span data-ttu-id="6c9b0-114">O destino de Processamento de Partições usa um gerenciador de conexões do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para se conectar ao projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém os cubos e as partições que o destino processa.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-114">The Partition Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the cubes and partitions the destination processes.</span></span> <span data-ttu-id="6c9b0-115">Para obter mais informações, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6c9b0-115">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="6c9b0-116">Esse destino tem uma entrada.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-116">This destination has one input.</span></span> <span data-ttu-id="6c9b0-117">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-117">It does not support an error output.</span></span>  
  
 <span data-ttu-id="6c9b0-118">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="6c9b0-119">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Destino** de Processamento de Partições, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6c9b0-119">For more information about the properties that you can set in the Partition Processing **Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="6c9b0-120">Editor de Destino de Processamento de Partições &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="6c9b0-120">Partition Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../partition-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="6c9b0-121">Editor de Destino de Processamento de Partições &#40;Página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="6c9b0-121">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../partition-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="6c9b0-122">Editor de Destino de Processamento de Partições &#40;Página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="6c9b0-122">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../partition-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="6c9b0-123">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="6c9b0-124">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6c9b0-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="6c9b0-125">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="6c9b0-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="6c9b0-126">Propriedades personalizadas do destino Processamento de Partições</span><span class="sxs-lookup"><span data-stu-id="6c9b0-126">Partition Processing Destination Custom Properties</span></span>](partition-processing-destination-custom-properties.md)  
  
 <span data-ttu-id="6c9b0-127">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6c9b0-127">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
