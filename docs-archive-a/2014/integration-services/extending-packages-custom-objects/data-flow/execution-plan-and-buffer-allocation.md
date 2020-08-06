---
title: Plano de execução e alocação de buffer | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom data flow components [Integration Services], buffer allocations
- custom data flow components [Integration Services], execution plans
- buffer allocations [Integration Services]
- data flow components [Integration Services], buffer allocations
- data flow components [Integration Services], execution plans
- execution plans [Integration Services]
ms.assetid: 679d9ff0-641e-47c3-abb8-d1a7dcb279dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03b8bb22988ccf77f8920252ac2d600478c92f3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679449"
---
# <a name="execution-plan-and-buffer-allocation"></a><span data-ttu-id="2f8f8-102">Plano de execução e alocação de buffer</span><span class="sxs-lookup"><span data-stu-id="2f8f8-102">Execution Plan and Buffer Allocation</span></span>
  <span data-ttu-id="2f8f8-103">Antes da execução, a tarefa de fluxo de dados examina seus componentes e gera um plano de execução para cada sequência de componentes.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-103">Before execution, the data flow task examines its components and generates an execution plan for each sequence of components.</span></span> <span data-ttu-id="2f8f8-104">Essa seção fornece detalhes sobre o plano de execução, como visualizá-lo e como buffers de entrada e saída são alocados com base no plano de execução.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-104">This section provides details about the execution plan, how to view the plan, and how input and output buffers are allocated based on the execution plan.</span></span>  
  
## <a name="understanding-the-execution-plan"></a><span data-ttu-id="2f8f8-105">Compreendendo o plano de execução</span><span class="sxs-lookup"><span data-stu-id="2f8f8-105">Understanding the Execution Plan</span></span>  
 <span data-ttu-id="2f8f8-106">Um plano de execução contém threads de origem e threads de trabalho, e cada thread contém listas de trabalho que especificam listas de trabalho de saída para threads de origem ou listas de trabalho de entrada e saída para threads de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-106">An execution plan contains source threads and work threads, and each thread contains work lists that specify output work lists for source threads or input and output work lists for work threads.</span></span> <span data-ttu-id="2f8f8-107">Os threads de origem em um plano de execução representam os componentes de origem no fluxo de dados e são identificados no plano de execução por *SourceThread\*\*n*, em que *n* é o número com base em zero do thread de origem.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-107">The source threads in an execution plan represent the source components in the data flow and are identified in the execution plan by *SourceThread\*\*n*, where *n* is the zero-based number of the source thread.</span></span>  
  
 <span data-ttu-id="2f8f8-108">Cada thread de origem cria um buffer, define um ouvinte e chama o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> no componente de origem.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-108">Each source thread creates a buffer, sets a listener, and calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method on the source component.</span></span> <span data-ttu-id="2f8f8-109">É nesse ponto que a execução é iniciada e dados são gerados, pois o componente de origem começa a adicionar linhas aos buffers de saída fornecidos pela tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-109">This is where execution starts and data originates, as the source component starts adding rows to the output buffers that are provided to it by the data flow task.</span></span> <span data-ttu-id="2f8f8-110">Depois do início da execução dos threads de origem, o balanço do trabalho é distribuído entre os threads de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-110">After the source threads are running, the balance of work is distributed among work threads.</span></span>  
  
 <span data-ttu-id="2f8f8-111">Um thread de trabalho pode conter listas de trabalho de entrada e saída e é identificado no plano de execução como *WorkThread\*\*n*, em que *n* é o número com base em zero do thread de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-111">A work thread may contain both input and output work lists and is identified in the execution plan as *WorkThread\*\*n*, where *n* is the zero-based number of the work thread.</span></span> <span data-ttu-id="2f8f8-112">Esses threads contêm listas de trabalho de saída quando o gráfico contém um componente com saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-112">These threads contain output work lists when the graph contains a component with asynchronous outputs.</span></span>  
  
 <span data-ttu-id="2f8f8-113">O exemplo de plano de execução a seguir representa um fluxo de dados que contém um componente de origem conectado a uma transformação com uma saída assíncrona conectada a um componente de destino.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-113">The following sample execution plan represents a data flow that contains a source component connected to a transformation with an asynchronous output connected to a destination component.</span></span> <span data-ttu-id="2f8f8-114">Nesse exemplo, o WorkThread0 contém uma lista de trabalho de saída porque o componente de transformação possui uma saída assíncrona.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-114">In this example, WorkThread0 contains an output work list because the transformation component has an asynchronous output.</span></span>  
  
```  
SourceThread0   
    Influences: 72 158   
    Output Work List   
        CreatePrimeBuffer of type 1 for output id 10   
        SetBufferListener: "WorkThread0" for input ID 73   
        CallPrimeOutput on component "OLE DB Source" (1)   
    End Output Work List   
    This thread drives 0 distributors   
End SourceThread0   
WorkThread0   
    Influences: 72 158   
    Input Work list, input ID 73   
        CallProcessInput on input ID 73 on component "Sort" (72) for view type 2   
    End Input Work list for input 73   
    Output Work List   
        CreatePrimeBuffer of type 3 for output id 74   
        SetBufferListener: "WorkThread1" for input ID 171with internal handoff   
        CallPrimeOutput on component "Sort" (72)   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread0   
WorkThread1   
    Influences: 158   
    Input Work list, input ID 171  
        CallProcessInput on input ID 171 on component "OLE DB Destination" (158) for view type 4  
    End Input Work list for input 171   
    Output Work List   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2f8f8-115">O plano de execução é gerado toda vez que um pacote é executado. Para capturá-lo, adicione um provedor de logs ao pacote, habilite o registro em log e selecione o evento **PipelineExecutionPlan**.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-115">The execution plan is generated every time a package is executed, and can be captured by adding a log provider to the package, enabling logging, and selecting the **PipelineExecutionPlan** event.</span></span>  
  
## <a name="understanding-buffer-allocation"></a><span data-ttu-id="2f8f8-116">Compreendendo a alocação de buffers</span><span class="sxs-lookup"><span data-stu-id="2f8f8-116">Understanding Buffer Allocation</span></span>  
 <span data-ttu-id="2f8f8-117">Com base no plano de execução, a tarefa de fluxo de dados cria buffers contendo as colunas definidas nas saídas dos componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-117">Based on the execution plan, the data flow task creates buffers that contain the columns defined in the outputs of the data flow components.</span></span> <span data-ttu-id="2f8f8-118">O buffer é reutilizado como os fluxos de dados pela sequência de componentes, até ser encontrado um componente com saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-118">The buffer is reused as the data flows through the sequence of components, until a component with asynchronous outputs is encountered.</span></span> <span data-ttu-id="2f8f8-119">Portanto, é criado um buffer novo, que contém as colunas de saída da saída assíncrona e as colunas de saída de componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-119">Then, a new buffer is created, which contains the output columns of the asynchronous output and the output columns of downstream components.</span></span>  
  
 <span data-ttu-id="2f8f8-120">Durante a execução, componentes têm acesso ao buffer na origem atual ou thread de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-120">During execution, components have access to the buffer in the current source or work thread.</span></span> <span data-ttu-id="2f8f8-121">O buffer é de entrada, fornecido pelo método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, ou de saída, fornecido pelo método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-121">The buffer is either an input buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, or an output buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="2f8f8-122">A propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> também identifica cada buffer como um buffer de entrada ou de saída.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> also identifies each buffer as an input or output buffer.</span></span>  
  
 <span data-ttu-id="2f8f8-123">Os componentes de transformação com saídas assíncronas recebem o buffer de entrada existente do método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> e recebem o novo buffer de saída do método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-123">Transformation components with asynchronous outputs receive the existing input buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, and receive the new output buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="2f8f8-124">Um componente de transformação com saídas assíncronas é o único tipo de componente de fluxo de dados que recebe um buffer de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-124">A transformation component with asynchronous outputs is the only type of data flow component that receives both an input and an output buffer.</span></span>  
  
 <span data-ttu-id="2f8f8-125">Como é provável que o buffer fornecido a um componente contenha mais colunas do que o componente possui em suas coleções de colunas de entrada ou saída, desenvolvedores de componentes podem chamar o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> para localizar uma coluna no buffer, especificando seu `LineageID`.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-125">Because the buffer provided to a component is likely to contain more columns than the component has in its input or output column collections, component developers can call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method to locate a column in the buffer by specifying its `LineageID`.</span></span>  
  
<span data-ttu-id="2f8f8-126">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-126">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2f8f8-127">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="2f8f8-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2f8f8-128">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="2f8f8-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2f8f8-129">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
