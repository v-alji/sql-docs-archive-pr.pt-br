---
title: Desenvolver um componente de transformação personalizado com saídas assíncronas | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom data flow components [Integration Services], transformation components
- asynchronous outputs [Integration Services]
- ProcessInput method
- cache [Integration Services]
- buffer allocations [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], transformation components
ms.assetid: 1c3e92c7-a4fa-4fdd-b9ca-ac3069536274
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41e2ecdf9f90765e75ff2b8c9c0681a25366e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683624"
---
# <a name="developing-a-custom-transformation-component-with-asynchronous-outputs"></a><span data-ttu-id="68f54-102">Desenvolvendo um componente de transformação personalizado com saídas assíncronas</span><span class="sxs-lookup"><span data-stu-id="68f54-102">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>
  <span data-ttu-id="68f54-103">Você usa um componente com saídas assíncronas quando uma transformação só consegue liberar linhas depois de o componente receber todas as suas linhas de saída, ou quando a transformação não gera exatamente uma linha de saída para cada linha recebida como entrada.</span><span class="sxs-lookup"><span data-stu-id="68f54-103">You use a component with asynchronous outputs when a transform cannot output rows until the component has received all its input rows, or when the transformation does not produce exactly one output row for each row received as input.</span></span> <span data-ttu-id="68f54-104">Por exemplo, a transformação Agregação só consegue calcular uma soma em linhas depois de ler todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="68f54-104">The Aggregate transformation, for example, cannot calculate a sum across rows until it has read all the rows.</span></span> <span data-ttu-id="68f54-105">Em contraste, você pode usar um componente com saídas síncronas a qualquer momento quando modifica cada linha de dados percorrida por ele.</span><span class="sxs-lookup"><span data-stu-id="68f54-105">In contrast, you can use a component with synchronous outputs any time when you modify each row of data as it passes through.</span></span> <span data-ttu-id="68f54-106">Você pode modificar os dados de cada linha estabelecida, ou criar uma ou mais colunas novas, cada qual com um valor para cada linha de entrada.</span><span class="sxs-lookup"><span data-stu-id="68f54-106">You can modify the data for each row in place, or you can create one or more new columns, each of which has a value for every one of the input rows.</span></span> <span data-ttu-id="68f54-107">Para obter mais informações sobre a diferença entre componentes síncronos e assíncronos, consulte [Compreender as transformações síncronas e assíncronas](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="68f54-107">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>

 <span data-ttu-id="68f54-108">Componentes de transformação com saídas assíncronas são exclusivos pois agem como componentes de destino e de origem.</span><span class="sxs-lookup"><span data-stu-id="68f54-108">Transformation components with asynchronous outputs are unique because they act as both destination and source components.</span></span> <span data-ttu-id="68f54-109">Esse tipo de componente recebe linhas de componentes upstream e adiciona linhas que são consumidas por componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="68f54-109">This kind of component receives rows from upstream components, and adds rows that are consumed by downstream components.</span></span> <span data-ttu-id="68f54-110">Nenhum outro componente de fluxo de dados executa essas duas operações.</span><span class="sxs-lookup"><span data-stu-id="68f54-110">No other data flow component performs both of these operations.</span></span>

 <span data-ttu-id="68f54-111">As colunas de componentes upstream que estão disponíveis para um componente com saídas síncronas estão automaticamente disponíveis para componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="68f54-111">The columns from upstream components that are available to a component with synchronous outputs are automatically available to components downstream from the component.</span></span> <span data-ttu-id="68f54-112">Portanto, um componente com saídas síncronas não precisa definir colunas de saída para fornecer colunas e linhas ao próximo componente.</span><span class="sxs-lookup"><span data-stu-id="68f54-112">Therefore, a component with synchronous outputs does not have to define any output columns to provide columns and rows to the next component.</span></span> <span data-ttu-id="68f54-113">Por outro lado, componentes com saídas assíncronas precisam definir colunas de saída e fornecer linhas a componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="68f54-113">Components with asynchronous outputs, on the other hand, must define output columns and provide rows to downstream components.</span></span> <span data-ttu-id="68f54-114">Portanto, um componente com saídas assíncronas precisa executar mais tarefas durante o tempo de design e execução, e o desenvolvedor de componentes precisa implementar mais códigos.</span><span class="sxs-lookup"><span data-stu-id="68f54-114">Therefore a component with asynchronous outputs has more tasks to perform during both design and execution time, and the component developer has more code to implement.</span></span>

 <span data-ttu-id="68f54-115">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contém várias transformações com saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="68f54-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contains several transformations with asynchronous outputs.</span></span> <span data-ttu-id="68f54-116">Por exemplo, a transformação Classificação precisa de todas as linhas para poder classificá-las, e consegue isso através de saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="68f54-116">For example, the Sort transformation requires all its rows before it can sort them, and achieves this by using asynchronous outputs.</span></span> <span data-ttu-id="68f54-117">Depois de receber todas as linhas, ela as classifica e as adiciona à sua saída.</span><span class="sxs-lookup"><span data-stu-id="68f54-117">After it has received all its rows, it sorts them and adds them to its output.</span></span>

 <span data-ttu-id="68f54-118">Essa seção explica detalhadamente como desenvolver transformações com saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="68f54-118">This section explains in detail how to develop transformations with asynchronous outputs.</span></span> <span data-ttu-id="68f54-119">Para obter mais informações sobre o desenvolvimento de componentes de origem, consulte [Desenvolver um componente de origem personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="68f54-119">For more information about source component development, see [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="68f54-120">Tempo de design</span><span class="sxs-lookup"><span data-stu-id="68f54-120">Design Time</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="68f54-121">Criando o componente</span><span class="sxs-lookup"><span data-stu-id="68f54-121">Creating the Component</span></span>
 <span data-ttu-id="68f54-122">A propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> do objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> identifica se uma saída é síncrona ou assíncrona.</span><span class="sxs-lookup"><span data-stu-id="68f54-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property on the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object identifies whether an output is synchronous or asynchronous.</span></span> <span data-ttu-id="68f54-123">Para criar uma saída assíncrona, adicione a saída ao componente e defina o <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> como zero.</span><span class="sxs-lookup"><span data-stu-id="68f54-123">To create an asynchronous output, add the output to the component and set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> to zero.</span></span> <span data-ttu-id="68f54-124">A definição dessa propriedade também determina se a tarefa de fluxo de dados aloca objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> parar a entrada e a saída do componente, ou se um único buffer é alocado e compartilhado entre os dois objetos.</span><span class="sxs-lookup"><span data-stu-id="68f54-124">Setting this property also determines whether the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects for both the input and output of the component, or whether a single buffer is allocated and shared between the two objects.</span></span>

 <span data-ttu-id="68f54-125">O código de exemplo a seguir mostra um componente que cria uma saída assíncrona em sua implementação <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="68f54-125">The following sample code shows a component that creates an asynchronous output in its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> implementation.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "AsyncComponent",ComponentType = ComponentType.Transform)]
    public class AsyncComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Call the base class, which adds a synchronous input
            // and output.
            base.ProvideComponentProperties();

            // Make the output asynchronous.
            IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
            output.SynchronousInputID = 0;
        }
    }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

<DtsPipelineComponent(DisplayName:="AsyncComponent", ComponentType:=ComponentType.Transform)> _
Public Class AsyncComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Call the base class, which adds a synchronous input
        ' and output.
        Me.ProvideComponentProperties()

        ' Make the output asynchronous.
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
        output.SynchronousInputID = 0

    End Sub

End Class
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="68f54-126">Criando e configurando colunas de saída</span><span class="sxs-lookup"><span data-stu-id="68f54-126">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="68f54-127">Conforme mencionado antes, um componente assíncrono adiciona colunas à sua coleção de colunas de saída para fornecer colunas a componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="68f54-127">As mentioned earlier, an asynchronous component adds columns to its output column collection to provide columns to downstream components.</span></span> <span data-ttu-id="68f54-128">Você pode escolher entre vários métodos de tempo de design, de acordo com as necessidades do componente.</span><span class="sxs-lookup"><span data-stu-id="68f54-128">There are several design-time methods to choose from, depending on the needs of the component.</span></span> <span data-ttu-id="68f54-129">Por exemplo, para passar todas as colunas dos componentes upstream para os componentes downstream, substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> para adicionar as colunas, pois esse é o primeiro método em que as colunas de entrada estão disponíveis para o componente.</span><span class="sxs-lookup"><span data-stu-id="68f54-129">For example, if you want to pass all the columns from the upstream components to the downstream components, you would override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> method to add the columns, because this is the first method in which the input columns are available to the component.</span></span>

 <span data-ttu-id="68f54-130">Se o componente criar colunas de saída com base nas colunas selecionadas para sua entrada, substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> para selecionar as colunas de saída e indicar como elas serão utilizadas.</span><span class="sxs-lookup"><span data-stu-id="68f54-130">If the component creates output columns based on the columns selected for its input, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> method to select the output columns and to indicate how they will be used.</span></span>

 <span data-ttu-id="68f54-131">Se um componente com saídas assíncronas criar colunas de saída com base nas colunas de componentes upstream e houver alterações nas colunas upstream disponíveis, o componente deverá atualizar sua coleção de colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="68f54-131">If a component with asynchronous outputs creates output columns based on the columns from upstream components, and the available upstream columns change, the component should update its output column collection.</span></span> <span data-ttu-id="68f54-132">Essas alterações devem ser detectadas pelo componente durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> e corrigidas durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="68f54-132">These changes should be detected by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and fixed during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span></span>

> [!NOTE]
>  <span data-ttu-id="68f54-133">Quando uma coluna de saída é removida da coleção de colunas de saída, os componentes downstream do fluxo de dados que referenciam a coluna são afetados negativamente.</span><span class="sxs-lookup"><span data-stu-id="68f54-133">When an output column is removed from the output column collection, downstream components in the data flow that reference the column are adversely affected.</span></span> <span data-ttu-id="68f54-134">A coluna de saída deve ser reparada sem remover e recriar a coluna para impedir a quebra de componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="68f54-134">The output column must be repaired without removing and recreating the column to prevent breaking the downstream components.</span></span> <span data-ttu-id="68f54-135">Por exemplo, se o tipo de dados da coluna for alterado, atualize-o.</span><span class="sxs-lookup"><span data-stu-id="68f54-135">For example, if the data type of the column has changed, you must update the data type.</span></span>

 <span data-ttu-id="68f54-136">O exemplo de código a seguir mostra um componente que adiciona uma coluna de saída à sua coleção de colunas de saída; esse procedimento ocorre em cada coluna disponível do componente upstream.</span><span class="sxs-lookup"><span data-stu-id="68f54-136">The following code example shows a component that adds an output column to its output column collection for each column available from the upstream component.</span></span>

```csharp
public override void OnInputPathAttached(int inputID)
{
   IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);
   IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
   IDTSVirtualInput100 vInput = input.GetVirtualInput();

   foreach (IDTSVirtualInputColumn100 vCol in vInput.VirtualInputColumnCollection)
   {
      IDTSOutputColumn100 outCol = output.OutputColumnCollection.New();
      outCol.Name = vCol.Name;
      outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage);
   }
}
```

```vb
Public Overrides Sub OnInputPathAttached(ByVal inputID As Integer)

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput()

    For Each vCol As IDTSVirtualInputColumn100 In vInput.VirtualInputColumnCollection

        Dim outCol As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        outCol.Name = vCol.Name
        outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage)

    Next
End Sub
```

## <a name="run-time"></a><span data-ttu-id="68f54-137">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="68f54-137">Run Time</span></span>
 <span data-ttu-id="68f54-138">Componentes com saídas assíncronas também executam, em tempo de execução, uma sequência diferente de métodos que outros tipos de componentes.</span><span class="sxs-lookup"><span data-stu-id="68f54-138">Components with asynchronous outputs also execute a different sequence of methods at run time than other types of components.</span></span> <span data-ttu-id="68f54-139">Primeiro, eles são os únicos componentes que recebem uma chamada para os métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="68f54-139">First, they are the only components that receive a call to both the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="68f54-140">Componentes com saídas assíncronas também precisam de acesso a todas as linhas recebidas para poder começar o processamento; portanto, eles precisam armazenar as linhas de entrada em cache internamente até a conclusão da leitura de todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="68f54-140">Components with asynchronous outputs also require access to all the incoming rows before they can start processing; therefore, they must cache the input rows internally until all rows have been read.</span></span> <span data-ttu-id="68f54-141">Finalmente, diferente de outros componentes, os componentes com saídas assíncronas recebem um buffer de entrada e um buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="68f54-141">Finally, unlike other components, components with asynchronous outputs receive both an input buffer and an output buffer.</span></span>

### <a name="understanding-the-buffers"></a><span data-ttu-id="68f54-142">Compreendendo os buffers</span><span class="sxs-lookup"><span data-stu-id="68f54-142">Understanding the Buffers</span></span>
 <span data-ttu-id="68f54-143">O componente recebe o buffer de entrada durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="68f54-143">The input buffer is received by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="68f54-144">Esse buffer contém as linhas adicionadas ao buffer por componentes upstream.</span><span class="sxs-lookup"><span data-stu-id="68f54-144">This buffer contains the rows added to the buffer by upstream components.</span></span> <span data-ttu-id="68f54-145">O buffer também contém as colunas de entrada do componente, além das colunas fornecidas na saída de um componente upstream, mas não adicionadas à coleção de entradas do componente assíncrono.</span><span class="sxs-lookup"><span data-stu-id="68f54-145">The buffer also contains the columns of the component's input, in addition to the columns that were provided in the output of an upstream component but were not added to the asynchronous component's input collection.</span></span>

 <span data-ttu-id="68f54-146">O buffer de saída, que é fornecido ao componente em <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, não contém linhas inicialmente.</span><span class="sxs-lookup"><span data-stu-id="68f54-146">The output buffer, which is provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, does not initially contain rows.</span></span> <span data-ttu-id="68f54-147">O componente adiciona linhas a esse buffer e fornece o buffer a componentes downstream quando está cheio.</span><span class="sxs-lookup"><span data-stu-id="68f54-147">The component adds rows to this buffer and provides the buffer to downstream components when it is full.</span></span> <span data-ttu-id="68f54-148">O buffer de saída contém as colunas definidas na coleção de colunas de saída do componente, além de quaisquer colunas adicionadas por outros componentes downstream às suas saídas.</span><span class="sxs-lookup"><span data-stu-id="68f54-148">The output buffer contains the columns defined in the component's output column collection, in addition to any columns that other downstream components have added to their outputs.</span></span>

 <span data-ttu-id="68f54-149">Os componentes com saídas síncronas se comportam de maneira diferente, pois recebem um único buffer compartilhado.</span><span class="sxs-lookup"><span data-stu-id="68f54-149">This is different behavior from that of components with synchronous outputs, which receive a single shared buffer.</span></span> <span data-ttu-id="68f54-150">O buffer compartilhado de um componente com saídas síncronas contém as colunas de entrada e saída do componente, além das colunas adicionadas às saídas dos componentes upstream e downstream.</span><span class="sxs-lookup"><span data-stu-id="68f54-150">The shared buffer of a component with synchronous outputs contains both the input and output columns of the component, in addition to columns added to the outputs of upstream and downstream components.</span></span>

### <a name="processing-rows"></a><span data-ttu-id="68f54-151">Processando linhas</span><span class="sxs-lookup"><span data-stu-id="68f54-151">Processing Rows</span></span>

#### <a name="caching-input-rows"></a><span data-ttu-id="68f54-152">Armazenando linhas de entrada em cache</span><span class="sxs-lookup"><span data-stu-id="68f54-152">Caching Input Rows</span></span>
 <span data-ttu-id="68f54-153">Ao escrever um componente com saídas assíncronas, você tem três opções para adicionar linhas ao buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="68f54-153">When you write a component with asynchronous outputs, you have three options for adding rows to the output buffer.</span></span> <span data-ttu-id="68f54-154">Você pode adicioná-las à medida que recebe linhas de entrada, armazená-las em cache até o componente receber todas as linhas do componente upstream ou adicioná-las quando for apropriado fazer isso para o componente.</span><span class="sxs-lookup"><span data-stu-id="68f54-154">You can add them as input rows are received, you can cache them until the component has received all the rows from the upstream component, or you can add them when it is appropriate to do so for the component.</span></span> <span data-ttu-id="68f54-155">O método escolhido depende dos requisitos do componente.</span><span class="sxs-lookup"><span data-stu-id="68f54-155">The method that you choose depends on the requirements of the component.</span></span> <span data-ttu-id="68f54-156">Por exemplo, o componente Classificação exige que todas as linhas upstream sejam recebidas antes de sua classificação.</span><span class="sxs-lookup"><span data-stu-id="68f54-156">For example, the Sort component requires that all the upstream rows be received before they can be sorted.</span></span> <span data-ttu-id="68f54-157">Portanto, ele aguarda a leitura de todas as linhas para poder adicioná-las ao buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="68f54-157">Therefore, it waits until all rows have been read before adding rows to the output buffer.</span></span>

 <span data-ttu-id="68f54-158">O componente deve armazenar em cache, internamente, as linhas recebidas no buffer de entrada, como preparação para processá-las.</span><span class="sxs-lookup"><span data-stu-id="68f54-158">The rows that are received in the input buffer must be cached internally by the component until it is ready to process them.</span></span> <span data-ttu-id="68f54-159">As linhas de buffer de entrada podem ser armazenadas em cache em uma tabela de dados, em uma matriz multidimensional ou em qualquer outra estrutura interna.</span><span class="sxs-lookup"><span data-stu-id="68f54-159">The incoming buffer rows can be cached in a data table, a multidimensional array, or any other internal structure.</span></span>

#### <a name="adding-output-rows"></a><span data-ttu-id="68f54-160">Adicionando linhas de saída</span><span class="sxs-lookup"><span data-stu-id="68f54-160">Adding Output Rows</span></span>
 <span data-ttu-id="68f54-161">Independentemente de adicionar linhas ao buffer de saída durante ou depois do recebimento de todas as linhas, você faz isso através do método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> no buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="68f54-161">Whether you add rows to the output buffer as they are received or after receiving all of the rows, you do so by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method on the output buffer.</span></span> <span data-ttu-id="68f54-162">Depois de adicionar a linha, defina os valores de cada coluna na linha nova.</span><span class="sxs-lookup"><span data-stu-id="68f54-162">After you have added the row, you set the values of each column in the new row.</span></span>

 <span data-ttu-id="68f54-163">Como às vezes há mais colunas no buffer de saída do que na coleção de colunas de saída do componente, localize o índice da coluna apropriada no buffer antes de definir seu valor.</span><span class="sxs-lookup"><span data-stu-id="68f54-163">Because there are sometimes more columns in the output buffer than in the output column collection of the component, you must locate the index of the appropriate column in the buffer before you can set its value.</span></span> <span data-ttu-id="68f54-164">O método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> retorna o índice da coluna na linha do buffer com o ID de linhagem especificado, que é utilizado para atribuir o valor à coluna do buffer.</span><span class="sxs-lookup"><span data-stu-id="68f54-164">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property returns the index of the column in the buffer row with the specified lineage ID, which is then used to assign the value to the buffer column.</span></span>

 <span data-ttu-id="68f54-165">O método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, que é chamado antes do método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> ou do método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, é o primeiro método em que a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> está disponível, e a primeira oportunidade de localizar os índices das colunas nos buffers de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="68f54-165">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, which is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method or the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, is the first method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property is available, and the first opportunity to locate the indexes of the columns in the input and output buffers.</span></span>

## <a name="sample"></a><span data-ttu-id="68f54-166">Amostra</span><span class="sxs-lookup"><span data-stu-id="68f54-166">Sample</span></span>
 <span data-ttu-id="68f54-167">O exemplo a seguir mostra um componente de transformação simples com saídas assíncronas que adiciona linhas ao buffer de saída à medida que as recebe.</span><span class="sxs-lookup"><span data-stu-id="68f54-167">The following sample shows a simple transformation component with asynchronous outputs that adds rows to the output buffer as they are received.</span></span> <span data-ttu-id="68f54-168">Esse exemplo não demonstra todos os métodos e todas as funcionalidades discutidas nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="68f54-168">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="68f54-169">Ele demonstra os métodos importantes que todo componente de transformação personalizado com saídas assíncronas deve substituir, mas não contém código para a validação em tempo de design.</span><span class="sxs-lookup"><span data-stu-id="68f54-169">It demonstrates the important methods that every custom transformation component with asynchronous outputs must override, but does not contain code for design-time validation.</span></span> <span data-ttu-id="68f54-170">Além disso, o código em <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> pressupõe que a coleção de colunas de saída contém uma coluna relativa a cada coluna da coleção de colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="68f54-170">Also, the code in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> assumes that the output column collection has one column for each column in the input column collection.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
   [DtsPipelineComponent(DisplayName = "AsynchronousOutput")]
   public class AsynchronousOutput : PipelineComponent
   {
      PipelineBuffer outputBuffer;
      int[] inputColumnBufferIndexes;
      int[] outputColumnBufferIndexes;

      public override void ProvideComponentProperties()
      {
         // Let the base class add the input and output objects.
         base.ProvideComponentProperties();

         // Name the input and output, and make the
         // output asynchronous.
         ComponentMetaData.InputCollection[0].Name = "Input";
         ComponentMetaData.OutputCollection[0].Name = "AsyncOutput";
         ComponentMetaData.OutputCollection[0].SynchronousInputID = 0;
      }
      public override void PreExecute()
      {
         IDTSInput100 input = ComponentMetaData.InputCollection[0];
         IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

         inputColumnBufferIndexes = new int[input.InputColumnCollection.Count];
         outputColumnBufferIndexes = new int[output.OutputColumnCollection.Count];

         for (int col = 0; col < input.InputColumnCollection.Count; col++)
            inputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[col].LineageID);

         for (int col = 0; col < output.OutputColumnCollection.Count; col++)
            outputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[col].LineageID);

      }

      public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
      {
         if (buffers.Length != 0)
            outputBuffer = buffers[0];
      }
      public override void ProcessInput(int inputID, PipelineBuffer buffer)
      {
            // Advance the buffer to the next row.
            while (buffer.NextRow())
            {
               // Add a row to the output buffer.
               outputBuffer.AddRow();
               for (int x = 0; x < inputColumnBufferIndexes.Length; x++)
               {
                  // Copy the data from the input buffer column to the output buffer column.
                  outputBuffer[outputColumnBufferIndexes[x]] = buffer[inputColumnBufferIndexes[x]];
               }
            }
         if (buffer.EndOfRowset)
         {
            // EndOfRowset on the input buffer is true.
            // Set EndOfRowset on the output buffer.
            outputBuffer.SetEndOfRowset();
         }
      }
   }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="AsynchronousOutput")> _
    Public Class AsynchronousOutput

        Inherits PipelineComponent

        Private outputBuffer As PipelineBuffer
        Private inputColumnBufferIndexes As Integer()
        Private outputColumnBufferIndexes As Integer()

        Public Overrides Sub ProvideComponentProperties()

            ' Let the base class add the input and output objects.
            Me.ProvideComponentProperties()

            ' Name the input and output, and make the
            ' output asynchronous.
            ComponentMetaData.InputCollection(0).Name = "Input"
            ComponentMetaData.OutputCollection(0).Name = "AsyncOutput"
            ComponentMetaData.OutputCollection(0).SynchronousInputID = 0
        End Sub

        Public Overrides Sub PreExecute()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)
            Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

            ReDim inputColumnBufferIndexes(input.InputColumnCollection.Count)
            ReDim outputColumnBufferIndexes(output.OutputColumnCollection.Count)

            For col As Integer = 0 To input.InputColumnCollection.Count
                inputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(col).LineageID)
            Next

            For col As Integer = 0 To output.OutputColumnCollection.Count
                outputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(col).LineageID)
            Next

        End Sub
        Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

            If buffers.Length <> 0 Then
                outputBuffer = buffers(0)
            End If

        End Sub

        Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

                ' Advance the buffer to the next row.
                While (buffer.NextRow())

                    ' Add a row to the output buffer.
                    outputBuffer.AddRow()
                    For x As Integer = 0 To inputColumnBufferIndexes.Length

                        ' Copy the data from the input buffer column to the output buffer column.
                        outputBuffer(outputColumnBufferIndexes(x)) = buffer(inputColumnBufferIndexes(x))

                    Next
                End While

            If buffer.EndOfRowset = True Then
                ' EndOfRowset on the input buffer is true.
                ' Set the end of row set on the output buffer.
                outputBuffer.SetEndOfRowset()
            End If
        End Sub
    End Class
End Namespace
```

<span data-ttu-id="68f54-171">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="68f54-171">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="68f54-172">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="68f54-172">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="68f54-173">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="68f54-173">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="68f54-174">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="68f54-174">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="68f54-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68f54-175">See Also</span></span>
 <span data-ttu-id="68f54-176">[Desenvolvendo um componente de transformação personalizado com saídas síncronas](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [entendendo transformações síncronas e assíncronas](../understanding-synchronous-and-asynchronous-transformations.md) [criando uma transformação assíncrona com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="68f54-176">[Developing a Custom Transformation Component with Synchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span></span>


