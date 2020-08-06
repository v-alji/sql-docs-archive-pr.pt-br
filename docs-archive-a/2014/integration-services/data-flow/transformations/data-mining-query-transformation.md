---
title: Transformação Consultas de Mineração de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquerytrans.f1
helpviewer_keywords:
- Data Mining Query transformation
- prediction queries [Integration Services]
ms.assetid: 7960133b-a3e1-48af-ba43-55ed78c38e71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 278fdc3b1abd38b63f01e967e28d11983a09e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569574"
---
# <a name="data-mining-query-transformation"></a><span data-ttu-id="8ed7f-102">Transformação Consulta de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="8ed7f-102">Data Mining Query Transformation</span></span>
  <span data-ttu-id="8ed7f-103">A transformação Consulta de Mineração de Dados executa consultas de previsão em relação a modelos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-103">The Data Mining Query transformation performs prediction queries against data mining models.</span></span> <span data-ttu-id="8ed7f-104">Essa transformação contém um construtor de consultas para criar consultas DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="8ed7f-104">This transformation contains a query builder for creating Data Mining Extensions (DMX) queries.</span></span> <span data-ttu-id="8ed7f-105">O construtor de consultas permite criar instruções personalizadas para avaliar os dados de entrada de transformação em relação a um modelo de mineração existente usando a linguagem DMX.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-105">The query builder lets you create custom statements for evaluating the transformation input data against an existing mining model using the DMX language.</span></span> <span data-ttu-id="8ed7f-106">Para obter mais informações, consulte [Referência de DMX &#40;extensões DMX&#41;](/sql/dmx/data-mining-extensions-dmx-reference).</span><span class="sxs-lookup"><span data-stu-id="8ed7f-106">For more information, see [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference).</span></span>  
  
 <span data-ttu-id="8ed7f-107">Uma transformação pode executar várias consultas de previsão se os modelos forem criados na mesma estrutura de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-107">One transformation can execute multiple prediction queries if the models are built on the same data mining structure.</span></span> <span data-ttu-id="8ed7f-108">Para obter mais informações, consulte [interfaces de consulta de mineração de dados](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span><span class="sxs-lookup"><span data-stu-id="8ed7f-108">For more information, see [Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span></span>  
  
## <a name="configuration-of-the-data-mining-query-transformation"></a><span data-ttu-id="8ed7f-109">Configuração da transformação Consulta de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="8ed7f-109">Configuration of the Data Mining Query Transformation</span></span>  
 <span data-ttu-id="8ed7f-110">A transformação de consulta de mineração de dados usa um gerenciador de conexões [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] para conectar-se ao projeto do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ou à instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] que contém a estrutura de mineração e modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-110">The Data Mining Query transformation uses an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models.</span></span> <span data-ttu-id="8ed7f-111">Para obter mais informações, consulte [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8ed7f-111">For more information, see [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="8ed7f-112">Essa transformação tem uma entrada e uma saída.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-112">This transformation has one input and one output.</span></span> <span data-ttu-id="8ed7f-113">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-113">It does not support an error output.</span></span>  
  
 <span data-ttu-id="8ed7f-114">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-114">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8ed7f-115">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação de Consultas de Mineração de Dados** , clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="8ed7f-115">For more information about the properties that you can set in the **Data Mining Query Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8ed7f-116">Editor de Transformação Consultas de Mineração de Dados &#40;Guia Modelo de Mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="8ed7f-116">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
-   [<span data-ttu-id="8ed7f-117">Editor de Transformação Consultas de Mineração de Dados &#40;Guia Modelo de Mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="8ed7f-117">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
 <span data-ttu-id="8ed7f-118">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="8ed7f-119">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="8ed7f-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8ed7f-120">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="8ed7f-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="8ed7f-121">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="8ed7f-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="8ed7f-122">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="8ed7f-122">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
