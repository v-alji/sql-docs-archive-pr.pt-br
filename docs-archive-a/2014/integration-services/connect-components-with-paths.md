---
title: Conectar componentes com caminhos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], connections
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 05633e4c-1370-4b05-802b-f36b07dd71c8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e11955601406406abe48b53197e95c8224762fee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684294"
---
# <a name="connect-components-with-paths"></a><span data-ttu-id="e3a0e-102">Conectar componentes com caminhos</span><span class="sxs-lookup"><span data-stu-id="e3a0e-102">Connect Components with Paths</span></span>
  <span data-ttu-id="e3a0e-103">Você constrói o fluxo de dados em um pacote na superfície de design da guia **Fluxo de Dados** no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3a0e-103">You construct the data flow in a package on the design surface of the **Data Flow** tab in the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e3a0e-104">Se o fluxo de dados contiver dois componentes de fluxo de dados, você poderá conectá-los vinculando a saída de uma fonte ou transformação à entrada de uma transformação ou destino.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-104">If a data flow contains two data flow components, you can connect them by connecting the output of a source or transformation to the input of a transformation or destination.</span></span> <span data-ttu-id="e3a0e-105">O conector entre dois componentes de fluxo de dados é chamado de caminho.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-105">The connector between two data flow components is called a path.</span></span>

 <span data-ttu-id="e3a0e-106">O diagrama a seguir mostra um simples fluxo de dados com um componente de fonte, duas transformações, um componente de destino e os caminhos que os conecta.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-106">The following diagram shows a simple data flow with a source component, two transformations, a destination component, and the paths that connect them.</span></span>

 <span data-ttu-id="e3a0e-107">![Fluxo de dados](media/mw-dts-08.gif "Fluxo de dados")</span><span class="sxs-lookup"><span data-stu-id="e3a0e-107">![Data flow](media/mw-dts-08.gif "Data flow")</span></span>

 <span data-ttu-id="e3a0e-108">Depois de dois componentes terem sido conectados, você pode visualizar os metadados dos dados que se movimentam através do caminho e as propriedades do caminho em **Editor de Caminho de Fluxo de Dados**.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-108">After two components are connected, you can view the metadata of the data that moves through the path and the properties of the path in **Data Flow Path Editor**.</span></span> <span data-ttu-id="e3a0e-109">Para obter mais informações, consulte [Integration Services Paths](data-flow/integration-services-paths.md).</span><span class="sxs-lookup"><span data-stu-id="e3a0e-109">For more information, see [Integration Services Paths](data-flow/integration-services-paths.md).</span></span>

 <span data-ttu-id="e3a0e-110">Você também pode adicionar os visualizadores de dados aos caminhos.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-110">You can also add data viewers to paths.</span></span> <span data-ttu-id="e3a0e-111">Um visualizador de dados torna possível visualizar os dados que se movem entre os componentes de fluxo de dados quando o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="e3a0e-111">A data viewer makes it possible to view data moving between data flow components when the package is run.</span></span>

### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="e3a0e-112">Para conectar os componentes em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="e3a0e-112">To connect components in a data flow</span></span>

-   [<span data-ttu-id="e3a0e-113">Conectar componentes em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="e3a0e-113">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)

### <a name="to-set-path-properties"></a><span data-ttu-id="e3a0e-114">Para definir as propriedades do caminho</span><span class="sxs-lookup"><span data-stu-id="e3a0e-114">To set path properties</span></span>

-   [<span data-ttu-id="e3a0e-115">Definir as propriedades de um caminho por meio do Editor de Caminho do Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="e3a0e-115">Set the Properties of a Path by Using the Data Flow Path Editor</span></span>](../../2014/integration-services/set-the-properties-of-a-path-by-using-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="e3a0e-116">Para exibir os metadados do caminho</span><span class="sxs-lookup"><span data-stu-id="e3a0e-116">To view path metadata</span></span>

-   [<span data-ttu-id="e3a0e-117">Exibir metadados do caminho no Editor de Caminho do Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="e3a0e-117">View Path Metadata in the Data Flow Path Editor</span></span>](../../2014/integration-services/view-path-metadata-in-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="e3a0e-118">Para exibir os metadados do caminho</span><span class="sxs-lookup"><span data-stu-id="e3a0e-118">To view path metadata</span></span>

-   [<span data-ttu-id="e3a0e-119">Adicionar um visualizador de dados a um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="e3a0e-119">Add a Data Viewer to a Data Flow</span></span>](../../2014/integration-services/add-a-data-viewer-to-a-data-flow.md)

## <a name="see-also"></a><span data-ttu-id="e3a0e-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3a0e-120">See Also</span></span>
 <span data-ttu-id="e3a0e-121">[Fluxo de dados](data-flow/data-flow.md) da [tarefa fluxo](control-flow/data-flow-task.md) de dados transformar dados com o [tratamento de erros de](data-flow/error-handling-in-data.md) [transformações](data-flow/transformations/transform-data-with-transformations.md) nos dados</span><span class="sxs-lookup"><span data-stu-id="e3a0e-121">[Data Flow Task](control-flow/data-flow-task.md) [Data Flow](data-flow/data-flow.md) [Transform Data with Transformations](data-flow/transformations/transform-data-with-transformations.md) [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>


