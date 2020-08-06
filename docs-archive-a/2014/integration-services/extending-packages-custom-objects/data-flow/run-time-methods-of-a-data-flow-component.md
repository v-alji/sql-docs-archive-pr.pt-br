---
title: Métodos de tempo de execução de um componente de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- run-time [Integration Services]
- data flow components [Integration Services], run-time methods
ms.assetid: fd9e4317-18dd-43af-bbdc-79db32183ac4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df0afe4c29044541c5a57aa3a466283ab4fe4fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681801"
---
# <a name="run-time-methods-of-a-data-flow-component"></a><span data-ttu-id="08c38-102">Métodos de tempo de execução de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="08c38-102">Run-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="08c38-103">No tempo de execução, a tarefa de fluxo de dados examina a sequência de componentes, prepara um plano de execução e gerencia um pool de threads de trabalho que executa o plano de trabalho.</span><span class="sxs-lookup"><span data-stu-id="08c38-103">At run time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="08c38-104">A tarefa carrega linhas de dados de origens, processa essas linhas através de transformações e as salva em destinos.</span><span class="sxs-lookup"><span data-stu-id="08c38-104">The task loads rows of data from sources, processes them through transformations, then saves them to destinations.</span></span>  
  
## <a name="sequence-of-method-execution"></a><span data-ttu-id="08c38-105">Sequência de execução do método</span><span class="sxs-lookup"><span data-stu-id="08c38-105">Sequence of Method Execution</span></span>  
 <span data-ttu-id="08c38-106">Durante a execução de um componente de fluxo de dados, um subconjunto dos métodos na classe base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> é chamado.</span><span class="sxs-lookup"><span data-stu-id="08c38-106">During the execution of a data flow component, a subset of the methods in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is called.</span></span> <span data-ttu-id="08c38-107">Os métodos e a sequência na qual eles são chamados são sempre os mesmos, com exceção dos métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-107">The methods, and the sequence in which they are called, are always the same, with the exception of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="08c38-108">Esses dois métodos são chamados com base na existência e na configuração dos objetos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> de um componente.</span><span class="sxs-lookup"><span data-stu-id="08c38-108">These two methods are called based on the existence and configuration of a component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects.</span></span>  
  
 <span data-ttu-id="08c38-109">A lista seguinte mostra os métodos na ordem em que são chamados durante a execução do componente.</span><span class="sxs-lookup"><span data-stu-id="08c38-109">The following list shows the methods in the order in which they are called during component execution.</span></span> <span data-ttu-id="08c38-110">Observe que <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, quando chamado, é sempre chamado antes do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-110">Note that <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, when called, is always called before <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrepareForExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PostExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Cleanup%2A>  
  
### <a name="primeoutput-method"></a><span data-ttu-id="08c38-111">Método PrimeOutput</span><span class="sxs-lookup"><span data-stu-id="08c38-111">PrimeOutput Method</span></span>  
 <span data-ttu-id="08c38-112">O método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> é chamado quando um componente tem pelo menos uma saída anexada a um componente downstream por meio de um objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>, e a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> da saída é zero.</span><span class="sxs-lookup"><span data-stu-id="08c38-112">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called when a component has at least one output, attached to a downstream component through an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, and the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property of the output is zero.</span></span> <span data-ttu-id="08c38-113">O método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> é chamado para componentes de origem e para transformações com saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="08c38-113">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called for source components and for transformations with asynchronous outputs.</span></span> <span data-ttu-id="08c38-114">Ao contrário do método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> descrito abaixo, o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> só é chamado uma vez para cada componente que o requer.</span><span class="sxs-lookup"><span data-stu-id="08c38-114">Unlike the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method described below, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is only called once for each component that requires it.</span></span>  
  
### <a name="processinput-method"></a><span data-ttu-id="08c38-115">Método ProcessInput</span><span class="sxs-lookup"><span data-stu-id="08c38-115">ProcessInput Method</span></span>  
 <span data-ttu-id="08c38-116">O método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> é chamado para componentes que têm pelo menos uma entrada anexada a um componente upstream por um objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="08c38-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for components that have at least one input attached to an upstream component by an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object.</span></span> <span data-ttu-id="08c38-117">O método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> é chamado para componentes de destino e para transformações com saídas síncronas.</span><span class="sxs-lookup"><span data-stu-id="08c38-117">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for destination components and for transformations with synchronous outputs.</span></span> <span data-ttu-id="08c38-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> é chamado repetidamente até que não haja mais nenhuma linha para processamento de componentes upstream.</span><span class="sxs-lookup"><span data-stu-id="08c38-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> is called repeatedly until there are no more rows to process from upstream components.</span></span>  
  
## <a name="working-with-inputs-and-outputs"></a><span data-ttu-id="08c38-119">Funcionando com entradas e saídas</span><span class="sxs-lookup"><span data-stu-id="08c38-119">Working with Inputs and Outputs</span></span>  
 <span data-ttu-id="08c38-120">Em tempo de execução, componentes de fluxo de dados executam as tarefas seguintes:</span><span class="sxs-lookup"><span data-stu-id="08c38-120">At run time, data flow components perform the following tasks:</span></span>  
  
-   <span data-ttu-id="08c38-121">Componentes de origem adicionam linhas.</span><span class="sxs-lookup"><span data-stu-id="08c38-121">Source components add rows.</span></span>  
  
-   <span data-ttu-id="08c38-122">Componentes de transformação com saídas síncronas recebem linhas fornecidas por componentes de origem.</span><span class="sxs-lookup"><span data-stu-id="08c38-122">Transformation components with synchronous outputs receive rows provided by source components.</span></span>  
  
-   <span data-ttu-id="08c38-123">Componentes de transformação com saídas assíncronas recebem linhas e adicionam linhas.</span><span class="sxs-lookup"><span data-stu-id="08c38-123">Transformation components with asynchronous outputs receive rows and add rows.</span></span>  
  
-   <span data-ttu-id="08c38-124">Componentes de destino recebem linhas e as carregam em um destino.</span><span class="sxs-lookup"><span data-stu-id="08c38-124">Destination components receive rows and then load them into a destination.</span></span>  
  
 <span data-ttu-id="08c38-125">Durante a execução, a tarefa de fluxo de dados aloca objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> que contêm todas as colunas definidas nas coleções de colunas de saída de uma sequência de componentes.</span><span class="sxs-lookup"><span data-stu-id="08c38-125">During execution, the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain all the columns defined in the output column collections of a sequence of components.</span></span> <span data-ttu-id="08c38-126">Por exemplo, se cada um dos quatro componentes em uma sequência de fluxo de dados adicionar uma coluna de saída à sua coleção de colunas de saída, o buffer fornecido a cada componente conterá quatro colunas, uma para cada coluna de saída por componente.</span><span class="sxs-lookup"><span data-stu-id="08c38-126">For example, if each of four components in a data flow sequence adds one output column to its output column collection,the buffer that is provided to each component contains four columns, one for each output column per component.</span></span> <span data-ttu-id="08c38-127">Por causa desse comportamento, às vezes um componente recebe buffers que contêm colunas que ele não usa.</span><span class="sxs-lookup"><span data-stu-id="08c38-127">Because of this behavior, a component sometimes receives buffers that contain columns it does not use.</span></span>  
  
 <span data-ttu-id="08c38-128">Como os buffers recebidos pelo seu componente podem conter colunas que o componente não vai usar, você deve localizar as colunas que quer usar nas coleções de colunas de entrada e saída do seu componente no buffer fornecido ao componente pela tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="08c38-128">Since the buffers received by your component may contain columns that the component will not use, you must locate the columns that you want to use in your component's input and output column collections in the buffer provided to the component by the data flow task.</span></span> <span data-ttu-id="08c38-129">Para isso, use o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-129">You do this by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property.</span></span> <span data-ttu-id="08c38-130">Por razões de desempenho, essa tarefa é executada ordinariamente durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, em lugar de em <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> ou <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-130">For performance reasons, this task is ordinarily performed during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, rather than in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
 <span data-ttu-id="08c38-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> é chamado antes dos métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, e é a primeira oportunidade para um componente realizar esse trabalho depois que <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> fica disponível para o componente.</span><span class="sxs-lookup"><span data-stu-id="08c38-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods, and is the first opportunity for a component to perform this work after the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> becomes available to the component.</span></span> <span data-ttu-id="08c38-132">Durante esse método, o componente deve localizar suas colunas nos buffers e armazenar essas informações internamente, de forma que as colunas possam ser usadas nos métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> ou <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-132">During this method, the component should locate its columns in the buffers and store this information internally so the columns can be used in either the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span>  
  
 <span data-ttu-id="08c38-133">O exemplo de código seguinte demonstra como um componente de transformação com uma saída síncrona localiza suas colunas de entrada no buffer durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-133">The following code example demonstrates how a transformation component with a synchronous output locates its input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span>  
  
```csharp  
private int []bufferColumnIndex;  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    bufferColumnIndex = new int[input.InputColumnCollection.Count];  
  
    for( int x=0; x < input.InputColumnCollection.Count; x++)  
    {  
        IDTSInputColumn100 column = input.InputColumnCollection[x];  
        bufferColumnIndex[x] = BufferManager.FindColumnByLineageID( input.Buffer, column.LineageID);  
    }  
}  
```  
  
```vb  
Dim bufferColumnIndex As Integer()  
  
    Public Overrides Sub PreExecute()  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
  
        ReDim bufferColumnIndex(input.InputColumnCollection.Count)  
  
        For x As Integer = 0 To input.InputColumnCollection.Count  
  
            Dim column As IDTSInputColumn100 = input.InputColumnCollection(x)  
            bufferColumnIndex(x) = BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID)  
  
        Next  
  
    End Sub  
```  
  
### <a name="adding-rows"></a><span data-ttu-id="08c38-134">Adicionando linhas</span><span class="sxs-lookup"><span data-stu-id="08c38-134">Adding Rows</span></span>  
 <span data-ttu-id="08c38-135">Os componentes fornecem linhas a componentes downstream acrescentando linhas aos objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="08c38-135">Components supply rows to downstream components by adding rows to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="08c38-136">A tarefa de fluxo de dados fornece uma matriz de buffers de saída – uma para cada objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> que é conectado a um componente downstream – como um parâmetro para o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-136">The data flow task provides an array of output buffers - one for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that is connected to a downstream component - as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="08c38-137">Os componentes de origem e os componentes de transformação com saídas assíncronas acrescentam linhas aos buffers e chamam o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> quando terminam de adicionar linhas.</span><span class="sxs-lookup"><span data-stu-id="08c38-137">Source components and transformation components with asynchronous outputs add rows to the buffers and call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method when they are finished adding rows.</span></span> <span data-ttu-id="08c38-138">A tarefa de fluxo de dados gerencia os buffers de saída que fornece aos componentes e, quando um buffer fica cheio, automaticamente move as linhas do buffer para o próximo componente.</span><span class="sxs-lookup"><span data-stu-id="08c38-138">The data flow task manages the output buffers that it supplies to components and, as a buffer becomes full, automatically moves the rows in the buffer to the next component.</span></span> <span data-ttu-id="08c38-139">O método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> é chamado uma vez por componente, ao contrário do método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, que é chamado repetidamente.</span><span class="sxs-lookup"><span data-stu-id="08c38-139">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is called one time per component, unlike  the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, which is called repeatedly.</span></span>  
  
 <span data-ttu-id="08c38-140">O exemplo de código seguinte demonstra como um componente acrescenta linhas aos seus buffers de saída durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, em seguida chama o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-140">The following code example demonstrates how a component adds rows to its output buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method, then calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method.</span></span>  
  
```csharp  
public override void PrimeOutput( int outputs, int []outputIDs,PipelineBuffer []buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        IDTSOutput100 output = ComponentMetaData.OutputCollection.GetObjectByID( outputIDs[x]);  
        PipelineBuffer buffer = buffers[x];  
  
        // TODO: Add rows to the output buffer.  
    }  
    foreach( PipelineBuffer buffer in buffers )  
    {  
        /// Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset();  
    }  
}  
```  
  
```vb  
public overrides sub PrimeOutput( outputs as Integer , outputIDs() as Integer ,buffers() as PipelineBuffer buffers)  
  
    For x As Integer = 0 To outputs.MaxValue  
  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.GetObjectByID(outputIDs(x))  
        Dim buffer As PipelineBuffer = buffers(x)  
  
        ' TODO: Add rows to the output buffer.  
  
    Next  
  
    For Each buffer As PipelineBuffer In buffers  
  
        ' Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset()  
  
    Next  
  
End Sub  
```  
  
 <span data-ttu-id="08c38-141">Para obter mais informações sobre o desenvolvimento de componentes que adicionam linhas a buffers de saída, consulte [Desenvolver um componente de origem personalizado](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) e [Desenvolver um componente de transformação personalizado com saídas assíncronas](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="08c38-141">For more information about developing components that add rows to output buffers, see [Developing a Custom Source Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) and [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span>  
  
### <a name="receiving-rows"></a><span data-ttu-id="08c38-142">Recebendo linhas</span><span class="sxs-lookup"><span data-stu-id="08c38-142">Receiving Rows</span></span>  
 <span data-ttu-id="08c38-143">Os componentes recebem linhas de componentes upstream em objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="08c38-143">Components receive rows from upstream components in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="08c38-144">A tarefa de fluxo de dados fornece um objeto <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> que contém as linhas adicionadas ao fluxo de dados pelos componentes upstream como um parâmetro para o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-144">The data flow task provides a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> object that contains the rows added to the data flow by upstream components as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="08c38-145">Esse buffer de entrada pode ser usado para examinar e modificar as linhas e colunas no buffer, mas não pode ser usado para adicionar ou remover linhas.</span><span class="sxs-lookup"><span data-stu-id="08c38-145">This input buffer can be used to examine and modify the rows and columns in the buffer, but cannot be used to add or remove rows.</span></span> <span data-ttu-id="08c38-146">O método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> é chamado repetidamente até que não haja mais nenhum buffer disponível.</span><span class="sxs-lookup"><span data-stu-id="08c38-146">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method is called repeatedly until there are no more available buffers.</span></span> <span data-ttu-id="08c38-147">Na última vez que é chamado, a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> é `true`.</span><span class="sxs-lookup"><span data-stu-id="08c38-147">The last time it is called, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="08c38-148">Você pode repetir a coleção de linhas no buffer usando o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A>, que avança o buffer à próxima linha.</span><span class="sxs-lookup"><span data-stu-id="08c38-148">You can iterate over the collection of rows in the buffer by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method, which advances the buffer to the next row.</span></span> <span data-ttu-id="08c38-149">Esse método retorna `false` quando o buffer está na última linha da coleção.</span><span class="sxs-lookup"><span data-stu-id="08c38-149">This method returns `false` when the buffer is on the last row in the collection.</span></span> <span data-ttu-id="08c38-150">Não é necessário verificar a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>, a menos que você tenha de executar uma ação adicional depois que as últimas linhas de dados forem processadas.</span><span class="sxs-lookup"><span data-stu-id="08c38-150">You do not have to check the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property unless you have to perform an additional action after the last rows of data have been processed.</span></span>  
  
 <span data-ttu-id="08c38-151">O texto abaixo mostra o padrão correto para usar o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> e a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>:</span><span class="sxs-lookup"><span data-stu-id="08c38-151">The following text shows the correct pattern for using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property:</span></span>  
  
 `while (buffer.NextRow())`  
  
 `{`  
  
 `// Do something with each row.`  
  
 `}`  
  
 `if (buffer.EndOfRowset)`  
  
 `{`  
  
 `// Optionally, do something after all rows have been processed.`  
  
 `}`  
  
 <span data-ttu-id="08c38-152">O exemplo de código a seguir demonstra como um componente processa as linhas em buffers de entrada durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c38-152">The following code example demonstrates how a component processes the rows in input buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput( int inputID, PipelineBuffer buffer )  
{  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
        while( buffer.NextRow())  
        {  
            // TODO: Examine the columns in the current row.  
        }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)  
        While buffer.NextRow() = True  
  
            ' TODO: Examine the columns in the current row.  
        End While  
  
End Sub  
```  
  
 <span data-ttu-id="08c38-153">Para obter mais informações sobre o desenvolvimento de componentes que recebem linhas em buffers de entrada, consulte [Desenvolver um componente de destino personalizado](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) e [Desenvolver um componente de transformação personalizado com saídas síncronas](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="08c38-153">For more information about developing components that receive rows in input buffers, see [Developing a Custom Destination Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) and [Developing a Custom Transformation Component with Synchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span></span>  
  
<span data-ttu-id="08c38-154">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="08c38-154">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="08c38-155">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="08c38-155">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="08c38-156">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="08c38-156">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="08c38-157">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="08c38-157">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c38-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08c38-158">See Also</span></span>  
 [<span data-ttu-id="08c38-159">Métodos de tempo de design de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="08c38-159">Design-time Methods of a Data Flow Component</span></span>](design-time-methods-of-a-data-flow-component.md)  
  
  
