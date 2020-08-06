---
title: Caminhos do Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- paths [Integration Services], about paths
- data flow [Integration Services], paths
- paths [Integration Services]
- destinations [Integration Services], paths
- sources [Integration Services], paths
ms.assetid: 6c4629a9-2ede-4011-9101-3b342249640e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c52bbd06974311a7fc94b3058309399d70df0034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680593"
---
# <a name="integration-services-paths"></a><span data-ttu-id="ba933-102">Caminhos do Integration Services</span><span class="sxs-lookup"><span data-stu-id="ba933-102">Integration Services Paths</span></span>
  <span data-ttu-id="ba933-103">Um caminho conecta dois componentes em um fluxo de dados conectando a saída de um componente de fluxo de dados à entrada de outro componente.</span><span class="sxs-lookup"><span data-stu-id="ba933-103">A path connects two components in a data flow by connecting the output of one data flow component to the input of another component.</span></span> <span data-ttu-id="ba933-104">Um caminho tem uma origem e um destino.</span><span class="sxs-lookup"><span data-stu-id="ba933-104">A path has a source and a destination.</span></span> <span data-ttu-id="ba933-105">Por exemplo, se um caminho conectar uma origem OLE DB e uma transformação Classificação, a origem OLE DB será a origem do caminho e a transformação Classificação será o destino do caminho.</span><span class="sxs-lookup"><span data-stu-id="ba933-105">For example, if a path connects an OLE DB source and a Sort transformation, the OLE DB source is the source of the path, and the Sort transformation is the destination of the path.</span></span> <span data-ttu-id="ba933-106">A origem é o componente onde o caminho inicia, e o destino é o componente onde o caminho termina.</span><span class="sxs-lookup"><span data-stu-id="ba933-106">The source is the component where the path starts, and the destination is the component where the path ends.</span></span>  
  
 <span data-ttu-id="ba933-107">Se você executar um pacote no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] , será possível exibir os dados em um fluxo de dados anexando visualizadores de dados a um caminho.</span><span class="sxs-lookup"><span data-stu-id="ba933-107">If you run a package in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can view the data in a data flow by attaching data viewers to a path.</span></span> <span data-ttu-id="ba933-108">Um visualizador de dados pode ser configurado para exibir dados em uma grade.</span><span class="sxs-lookup"><span data-stu-id="ba933-108">A data viewer can be configured to display data in a grid.</span></span> <span data-ttu-id="ba933-109">Um visualizador de dados é uma ferramenta útil de depuração.</span><span class="sxs-lookup"><span data-stu-id="ba933-109">A data viewer is a useful debugging tool.</span></span> <span data-ttu-id="ba933-110">Para obter mais informações, consulte [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="ba933-110">For more information, see [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span></span>  
  
## <a name="configuration-of-the-path"></a><span data-ttu-id="ba933-111">Configuração do caminho</span><span class="sxs-lookup"><span data-stu-id="ba933-111">Configuration of the Path</span></span>  
 <span data-ttu-id="ba933-112">O Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] fornece a caixa de diálogo **Editor de Caminho do Fluxo de Dados** para definir propriedades de caminho, exibindo os metadados das colunas de dados que passam pelo caminho e configurando visualizadores de dados.</span><span class="sxs-lookup"><span data-stu-id="ba933-112">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides the **Data Flow Path Editor** dialog box for setting path properties, viewing the metadata of the data columns that pass through the path, and configuring data viewers.</span></span>  
  
 <span data-ttu-id="ba933-113">As propriedades de caminho configurável incluem o nome, a descrição e a anotação do caminho.</span><span class="sxs-lookup"><span data-stu-id="ba933-113">The configurable path properties include the name, description, and annotation of the path.</span></span> <span data-ttu-id="ba933-114">Você também pode configurar caminhos de forma programática.</span><span class="sxs-lookup"><span data-stu-id="ba933-114">You can also configure paths programmatically.</span></span> <span data-ttu-id="ba933-115">Para obter mais informações, consulte [Conectando componentes do fluxo de dados programaticamente](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="ba933-115">For more information, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
 <span data-ttu-id="ba933-116">Uma anotação de caminho exibe o nome da origem do caminho ou o nome do caminho na superfície de design da guia **Fluxo de Dados** no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba933-116">A path annotation displays the name of the path source or the path name on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="ba933-117">As anotações de caminho são semelhantes às anotações que você pode adicionar a fluxos de dados, fluxos de controle e manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="ba933-117">Path annotations are similar to the annotations you can add to data flows, control flows, and event handlers.</span></span> <span data-ttu-id="ba933-118">A única diferença é que uma anotação de caminho é anexada a um caminho, ao passo que outras anotações aparecem nas guias **Fluxo de Dados**, **Fluxo de Controle**e **Controle de Eventos**do Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba933-118">The only difference is that a path annotation is attached to a path, whereas other annotations appear on the **Data Flow**, **Control Flow**, and **Event Handle**r tabs of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="ba933-119">Os metadados exibem nome, tipo de dados, precisão, escala, comprimento, página de código e componente de origem de cada coluna na saída do componente anterior.</span><span class="sxs-lookup"><span data-stu-id="ba933-119">The metadata shows the name, data type, precision, scale, length, code page, and source component of each column in the output of the previous component.</span></span> <span data-ttu-id="ba933-120">O componente de origem é o componente de fluxo de dados que criou a coluna.</span><span class="sxs-lookup"><span data-stu-id="ba933-120">The source component is the data flow component that created the column.</span></span> <span data-ttu-id="ba933-121">Isso pode ou não ser o primeiro componente no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="ba933-121">This may or may not be the first component in the data flow.</span></span> <span data-ttu-id="ba933-122">Por exemplo, as transformações Union All e Classificação criam as próprias colunas e são as origens de suas colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="ba933-122">For example, the Union All and Sort transformations create their own columns, and they are the sources of their output columns.</span></span> <span data-ttu-id="ba933-123">Em contrapartida, uma transformação Copiar Coluna pode passar por colunas sem as alterá-las ou pode criar colunas novas copiando as colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="ba933-123">In contrast, a Copy Column transformation can pass through columns without changing them or can create new columns by copying input columns.</span></span> <span data-ttu-id="ba933-124">A transformação Copiar Coluna é o componente de origem somente das novas colunas.</span><span class="sxs-lookup"><span data-stu-id="ba933-124">The Copy Column transformation is the source component only of the new columns.</span></span>  
  
 <span data-ttu-id="ba933-125">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="ba933-125">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ba933-126">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Caminho do Fluxo de Dados** , clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ba933-126">For more information about the properties that you can set in the **Data Flow Path Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ba933-127">Editor de caminho de fluxo de dados &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="ba933-127">Data Flow Path Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="ba933-128">Editor de caminho de fluxo de dados &#40;página de metadados&#41;</span><span class="sxs-lookup"><span data-stu-id="ba933-128">Data Flow Path Editor &#40;Metadata Page&#41;</span></span>](../data-flow-path-editor-metadata-page.md)  
  
-   [<span data-ttu-id="ba933-129">Editor de caminho de fluxo de dados &#40;página visualizadores de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="ba933-129">Data Flow Path Editor &#40;Data Viewers Page&#41;</span></span>](../data-flow-path-editor-data-viewers-page.md)  
  
 <span data-ttu-id="ba933-130">Para obter mais informações sobre as propriedades que podem ser definidas programaticamente, consulte [Path Properties](../path-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ba933-130">For more information about the properties that you can set programmatically, see [Path Properties](../path-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ba933-131">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ba933-131">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ba933-132">Exibir metadados do caminho no Editor de Caminho do Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="ba933-132">View Path Metadata in the Data Flow Path Editor</span></span>](../view-path-metadata-in-the-data-flow-path-editor.md)  
  
-   [<span data-ttu-id="ba933-133">Conectar componentes em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="ba933-133">Connect Components in a Data Flow</span></span>](connect-components-in-a-data-flow.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba933-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba933-134">See Also</span></span>  
 [<span data-ttu-id="ba933-135">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="ba933-135">Data Flow</span></span>](data-flow.md)  
  
  
