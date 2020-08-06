---
title: Propriedades do caminho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- paths [Integration Services], properties
ms.assetid: 89b1e347-9579-4f6b-af74-c6519ea08eea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ca263b866fb6d5d7ceb6352f708f387d79cad4f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570098"
---
# <a name="path-properties"></a><span data-ttu-id="fb79a-102">Propriedades do caminho</span><span class="sxs-lookup"><span data-stu-id="fb79a-102">Path Properties</span></span>
  <span data-ttu-id="fb79a-103">Os objetos de fluxo de dados no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] modelo de objeto têm propriedades comuns e propriedades personalizadas no nível do componente, entradas e saídas e colunas de entrada e de saída.</span><span class="sxs-lookup"><span data-stu-id="fb79a-103">The data flow objects in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model have common properties and custom properties at the level of the component, inputs and outputs, and input columns and output columns.</span></span> <span data-ttu-id="fb79a-104">Muitas propriedades têm valores somente leitura, atribuídos em tempo de execução pelo mecanismo de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="fb79a-104">Many properties have read-only values that are assigned at run time by the data flow engine.</span></span>  
  
 <span data-ttu-id="fb79a-105">Esse tópico lista e descreve as propriedades personalizadas dos caminhos que conectam objetos do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="fb79a-105">This topic lists and describes the custom properties of the paths that connect data flow objects.</span></span>  
  
## <a name="path-properties"></a><span data-ttu-id="fb79a-106">Propriedades do caminho</span><span class="sxs-lookup"><span data-stu-id="fb79a-106">Path Properties</span></span>  
 <span data-ttu-id="fb79a-107">No modelo de objeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], um caminho que conecta componentes no fluxo de dados implementa a interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="fb79a-107">In the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model, a path that connects components in the data flow implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> interface.</span></span>  
  
 <span data-ttu-id="fb79a-108">A tabela a seguir descreve as propriedades configuráveis dos caminhos em um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="fb79a-108">The following table describes the configurable properties of the paths in a data flow.</span></span> <span data-ttu-id="fb79a-109">O mecanismo de fluxo de dados também atribui valores a propriedades somente leitura adicionais que não são listadas aqui.</span><span class="sxs-lookup"><span data-stu-id="fb79a-109">The data flow engine also assigns values to additional read-only properties that are not listed here.</span></span>  
  
|<span data-ttu-id="fb79a-110">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="fb79a-110">Property name</span></span>|<span data-ttu-id="fb79a-111">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="fb79a-111">Data Type</span></span>|<span data-ttu-id="fb79a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="fb79a-112">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="fb79a-113">PathAnnotation</span><span class="sxs-lookup"><span data-stu-id="fb79a-113">PathAnnotation</span></span>|<span data-ttu-id="fb79a-114">Inteiro (enumeração)</span><span class="sxs-lookup"><span data-stu-id="fb79a-114">Integer (enumeration)</span></span>|<span data-ttu-id="fb79a-115">Um valor que indica se uma anotação deve ser exibida com o caminho na superfície do designer.</span><span class="sxs-lookup"><span data-stu-id="fb79a-115">A value that indicates whether an annotation should be displayed with the path on the designer surface.</span></span> <span data-ttu-id="fb79a-116">Os valores possíveis são `AsNeeded`, `SourceName`, `PathName` e `Never`.</span><span class="sxs-lookup"><span data-stu-id="fb79a-116">The possible values are `AsNeeded`, `SourceName`, `PathName`, and `Never`.</span></span> <span data-ttu-id="fb79a-117">O valor padrão é `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="fb79a-117">The default value is `AsNeeded`.</span></span>|  
|<span data-ttu-id="fb79a-118">DestinationName</span><span class="sxs-lookup"><span data-stu-id="fb79a-118">DestinationName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>|<span data-ttu-id="fb79a-119">A entrada associada ao caminho.</span><span class="sxs-lookup"><span data-stu-id="fb79a-119">The input associated with the path.</span></span>|  
|<span data-ttu-id="fb79a-120">SourceName</span><span class="sxs-lookup"><span data-stu-id="fb79a-120">SourceName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>|<span data-ttu-id="fb79a-121">A saída associada ao caminho.</span><span class="sxs-lookup"><span data-stu-id="fb79a-121">The output associated with the path.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb79a-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb79a-122">See Also</span></span>  
 <span data-ttu-id="fb79a-123">[Caminhos do Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="fb79a-123">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="fb79a-124">[Propriedades comuns](../../2014/integration-services/common-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fb79a-124">[Common Properties](../../2014/integration-services/common-properties.md) </span></span>  
 <span data-ttu-id="fb79a-125">[Propriedades personalizadas da transformação](data-flow/transformations/transformation-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fb79a-125">[Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md) </span></span>  
 [<span data-ttu-id="fb79a-126">Propriedades de fluxo de dados que podem ser definidas usando expressões</span><span class="sxs-lookup"><span data-stu-id="fb79a-126">Data Flow Properties that Can Be Set by Using Expressions</span></span>](../../2014/integration-services/data-flow-properties-that-can-be-set-by-using-expressions.md)  
  
  
