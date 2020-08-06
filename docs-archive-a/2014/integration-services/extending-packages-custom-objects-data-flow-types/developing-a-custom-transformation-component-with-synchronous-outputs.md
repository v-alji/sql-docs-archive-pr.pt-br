---
title: Desenvolver um componente de transformação personalizado com saídas síncronas | Microsoft Docs
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
- ProcessInput method
- buffer allocations [Integration Services]
- synchronous outputs [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- data flow components [Integration Services], transformation components
ms.assetid: b694d21f-9919-402d-9192-666c6449b0b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 94d78872570103d3df7e1cb96aecb144fafe4257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683625"
---
# <a name="developing-a-custom-transformation-component-with-synchronous-outputs"></a><span data-ttu-id="faa30-102">Desenvolvendo um componente de transformação personalizado com saídas síncronas</span><span class="sxs-lookup"><span data-stu-id="faa30-102">Developing a Custom Transformation Component with Synchronous Outputs</span></span>
  <span data-ttu-id="faa30-103">Os componentes de transformação com saídas síncronas recebem linhas de componentes upstream e leem ou modificam os valores das colunas dessas linhas à medida que passam as linhas para os componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="faa30-103">Transformation components with synchronous outputs receive rows from upstream components, and read or modify the values in the columns of these rows as they pass the rows to downstream components.</span></span> <span data-ttu-id="faa30-104">Eles também podem definir colunas de saída adicionais derivadas das colunas fornecidas pelos componentes upstream, mas não acrescentam linhas ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="faa30-104">They may also define additional output columns that are derived from the columns provided by upstream components, but they do not add rows to the data flow.</span></span> <span data-ttu-id="faa30-105">Para obter mais informações sobre a diferença entre componentes síncronos e assíncronos, consulte [Compreender as transformações síncronas e assíncronas](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="faa30-105">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>  
  
 <span data-ttu-id="faa30-106">Esse tipo de componente é adequado para tarefas em que os dados são modificados em linha, à medida que são fornecidos ao componente, e o componente não tem que ver todas as linhas antes de processá-las.</span><span class="sxs-lookup"><span data-stu-id="faa30-106">This kind of component is suited for tasks where the data is modified inline as it is provided to the component and where the component does not have to see all the rows before processing them.</span></span> <span data-ttu-id="faa30-107">É o componente mais fácil a desenvolver por que as transformações com saídas síncronas em geral não se conectam a fontes de dados externas, gerenciam colunas de metadados externas ou adicionam linhas a buffers de saída.</span><span class="sxs-lookup"><span data-stu-id="faa30-107">It is the easiest component to develop because transformations with synchronous outputs typically do not connect to external data sources, manage external metadata columns, or add rows to output buffers.</span></span>  
  
 <span data-ttu-id="faa30-108">Criar um componente de transformação com saídas síncronas envolve adicionar um <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> contendo as colunas upstream selecionadas para o componente, e um objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> que podem conter colunas derivadas criadas pelo componente.</span><span class="sxs-lookup"><span data-stu-id="faa30-108">Creating a transformation component with synchronous outputs involves adding an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> that will contain the upstream columns selected for the component, and a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that may contain derived columns created by the component.</span></span> <span data-ttu-id="faa30-109">Também inclui a implementação de métodos de tempo de design e o fornecimento de um código que leia ou modifique as colunas nas linhas do buffer de entrada durante a execução.</span><span class="sxs-lookup"><span data-stu-id="faa30-109">It also includes implementing the design-time methods, and providing code that reads or modifies the columns in the incoming buffer rows during execution.</span></span>  
  
 <span data-ttu-id="faa30-110">Esta seção fornece as informações necessárias para implementar um componente de transformação personalizado e fornece exemplos de códigos para ajudar você a entender melhor os conceitos.</span><span class="sxs-lookup"><span data-stu-id="faa30-110">This section provides the information that is required to implement a custom transformation component, and provides code examples to help you better understand the concepts.</span></span>  
  
## <a name="design-time"></a><span data-ttu-id="faa30-111">Tempo de design</span><span class="sxs-lookup"><span data-stu-id="faa30-111">Design Time</span></span>  
 <span data-ttu-id="faa30-112">O código do tempo de design desse componente envolve a criação de entradas e saídas, a adição de qualquer coluna de saída adicional que o componente gere e a validação da configuração do componente.</span><span class="sxs-lookup"><span data-stu-id="faa30-112">The design-time code for this component involves creating the inputs and outputs, adding any additional output columns that the component generates, and validating the configuration of the component.</span></span>  
  
### <a name="creating-the-component"></a><span data-ttu-id="faa30-113">Criando o componente</span><span class="sxs-lookup"><span data-stu-id="faa30-113">Creating the Component</span></span>  
 <span data-ttu-id="faa30-114">As entradas, saídas e propriedades personalizadas do componente normalmente são criadas durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="faa30-114">The inputs, outputs, and custom properties of the component are typically created during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="faa30-115">Há dois modos de adicionar a entrada e a saída de um componente de transformação com saídas síncronas.</span><span class="sxs-lookup"><span data-stu-id="faa30-115">There are two ways that you can add the input and the output of a transformation component with synchronous outputs.</span></span> <span data-ttu-id="faa30-116">Você pode usar a implementação da classe base do método e modificar a entrada e a saída padrão que ele cria, ou adicionar explicitamente a entrada e a saída.</span><span class="sxs-lookup"><span data-stu-id="faa30-116">You can use the base class implementation of the method and then modify the default input and output that it creates, or you can explicitly add the input and output yourself.</span></span>  
  
 <span data-ttu-id="faa30-117">O exemplo de código a seguir mostra uma implementação de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> que explicitamente adiciona os objetos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="faa30-117">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that explicitly adds the input and output objects.</span></span> <span data-ttu-id="faa30-118">A chamada para a classe base que realizaria a mesma função é incluída em um comentário.</span><span class="sxs-lookup"><span data-stu-id="faa30-118">The call to the base class that would accomplish the same thing is included in a comment.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SynchronousComponent", ComponentType = ComponentType.Transform)]  
    public class SyncComponent : PipelineComponent  
    {  
  
        public override void ProvideComponentProperties()  
        {  
            // Add the input.  
            IDTSInput100 input = ComponentMetaData.InputCollection.New();  
            input.Name = "Input";  
  
            // Add the output.  
            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
            output.Name = "Output";  
            output.SynchronousInputID = input.ID;  
  
            // Alternatively, you can let the base class add the input and output  
            // and set the SynchronousInputID of the output to the ID of the input.  
            // base.ProvideComponentProperties();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsPipelineComponent(DisplayName:="SynchronousComponent", ComponentType:=ComponentType.Transform)> _  
Public Class SyncComponent  
    Inherits PipelineComponent  
  
    Public Overrides Sub ProvideComponentProperties()  
  
        ' Add the input.  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()  
        input.Name = "Input"  
  
        ' Add the output.  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()  
        output.Name = "Output"  
        output.SynchronousInputID = Input.ID  
  
        ' Alternatively, you can let the base class add the input and output  
        ' and set the SynchronousInputID of the output to the ID of the input.  
        ' base.ProvideComponentProperties();  
  
    End Sub  
  
End Class  
```  
  
### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="faa30-119">Criando e configurando colunas de saída</span><span class="sxs-lookup"><span data-stu-id="faa30-119">Creating and Configuring Output Columns</span></span>  
 <span data-ttu-id="faa30-120">Embora componentes de transformação com saídas síncronas não acrescentem linhas a buffers, eles podem acrescentar colunas de saída extras à sua saída.</span><span class="sxs-lookup"><span data-stu-id="faa30-120">Although transformation components with synchronous outputs do not add rows to buffers, they may add extra output columns to their output.</span></span> <span data-ttu-id="faa30-121">Normalmente, quando um componente adiciona uma coluna de saída, os valores dessa nova coluna são derivados em tempo de execução dos dados contidos em uma ou mais das colunas fornecidas ao componente por um componente upstream.</span><span class="sxs-lookup"><span data-stu-id="faa30-121">Typically, when a component adds an output column, the values for the new output column are derived at run time from the data that is contained in one or more of the columns provided to the component by an upstream component.</span></span>  
  
 <span data-ttu-id="faa30-122">Depois que uma coluna de saída foi criada, suas propriedades de tipo de dados devem ser definidas.</span><span class="sxs-lookup"><span data-stu-id="faa30-122">After an output column has been created, its data type properties must be set.</span></span> <span data-ttu-id="faa30-123">Definir as propriedades de tipo de dados de uma coluna de saída requer manipulação especial e é executado chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="faa30-123">Setting the data type properties of an output column requires special handling and is performed by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="faa30-124">Esse método é necessário por que as propriedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> são individualmente somente leitura, porque cada uma delas depende das configurações da outra.</span><span class="sxs-lookup"><span data-stu-id="faa30-124">This method is required because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are individually read-only, because each depends on the settings of the other.</span></span> <span data-ttu-id="faa30-125">Esse método garante que os valores das propriedades sejam definidos de forma consistente, e a tarefa de fluxo de dados valida se eles foram definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="faa30-125">This method guarantees that the values of the properties are set consistently, and the data flow task validates that they are set correctly.</span></span>  
  
 <span data-ttu-id="faa30-126">O <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> da coluna determina os valores que são definidos para as outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="faa30-126">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="faa30-127">A tabela a seguir mostra os requisitos nas propriedades dependentes para cada <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="faa30-127">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="faa30-128">Os tipos de dados não listados têm as propriedades dependentes definidas como zero.</span><span class="sxs-lookup"><span data-stu-id="faa30-128">The data types not listed have their dependent properties set to zero.</span></span>  
  
|<span data-ttu-id="faa30-129">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="faa30-129">DataType</span></span>|<span data-ttu-id="faa30-130">Comprimento</span><span class="sxs-lookup"><span data-stu-id="faa30-130">Length</span></span>|<span data-ttu-id="faa30-131">Escala</span><span class="sxs-lookup"><span data-stu-id="faa30-131">Scale</span></span>|<span data-ttu-id="faa30-132">Precisão</span><span class="sxs-lookup"><span data-stu-id="faa30-132">Precision</span></span>|<span data-ttu-id="faa30-133">CodePage</span><span class="sxs-lookup"><span data-stu-id="faa30-133">CodePage</span></span>|  
|--------------|------------|-----------|---------------|--------------|  
|<span data-ttu-id="faa30-134">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="faa30-134">DT_DECIMAL</span></span>|<span data-ttu-id="faa30-135">0</span><span class="sxs-lookup"><span data-stu-id="faa30-135">0</span></span>|<span data-ttu-id="faa30-136">Maior que 0 e menor ou igual a 28.</span><span class="sxs-lookup"><span data-stu-id="faa30-136">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="faa30-137">0</span><span class="sxs-lookup"><span data-stu-id="faa30-137">0</span></span>|<span data-ttu-id="faa30-138">0</span><span class="sxs-lookup"><span data-stu-id="faa30-138">0</span></span>|  
|<span data-ttu-id="faa30-139">DT_CY</span><span class="sxs-lookup"><span data-stu-id="faa30-139">DT_CY</span></span>|<span data-ttu-id="faa30-140">0</span><span class="sxs-lookup"><span data-stu-id="faa30-140">0</span></span>|<span data-ttu-id="faa30-141">0</span><span class="sxs-lookup"><span data-stu-id="faa30-141">0</span></span>|<span data-ttu-id="faa30-142">0</span><span class="sxs-lookup"><span data-stu-id="faa30-142">0</span></span>|<span data-ttu-id="faa30-143">0</span><span class="sxs-lookup"><span data-stu-id="faa30-143">0</span></span>|  
|<span data-ttu-id="faa30-144">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="faa30-144">DT_NUMERIC</span></span>|<span data-ttu-id="faa30-145">0</span><span class="sxs-lookup"><span data-stu-id="faa30-145">0</span></span>|<span data-ttu-id="faa30-146">Maior que 0 e menor ou igual a 28, e menor que a Precisão.</span><span class="sxs-lookup"><span data-stu-id="faa30-146">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="faa30-147">Maior ou igual a 1 e menor ou igual a 38.</span><span class="sxs-lookup"><span data-stu-id="faa30-147">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="faa30-148">0</span><span class="sxs-lookup"><span data-stu-id="faa30-148">0</span></span>|  
|<span data-ttu-id="faa30-149">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="faa30-149">DT_BYTES</span></span>|<span data-ttu-id="faa30-150">Maior que 0.</span><span class="sxs-lookup"><span data-stu-id="faa30-150">Greater than 0.</span></span>|<span data-ttu-id="faa30-151">0</span><span class="sxs-lookup"><span data-stu-id="faa30-151">0</span></span>|<span data-ttu-id="faa30-152">0</span><span class="sxs-lookup"><span data-stu-id="faa30-152">0</span></span>|<span data-ttu-id="faa30-153">0</span><span class="sxs-lookup"><span data-stu-id="faa30-153">0</span></span>|  
|<span data-ttu-id="faa30-154">DT_STR</span><span class="sxs-lookup"><span data-stu-id="faa30-154">DT_STR</span></span>|<span data-ttu-id="faa30-155">Maior que 0 e menor que 8000.</span><span class="sxs-lookup"><span data-stu-id="faa30-155">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="faa30-156">0</span><span class="sxs-lookup"><span data-stu-id="faa30-156">0</span></span>|<span data-ttu-id="faa30-157">0</span><span class="sxs-lookup"><span data-stu-id="faa30-157">0</span></span>|<span data-ttu-id="faa30-158">Não 0 e uma página de código válida.</span><span class="sxs-lookup"><span data-stu-id="faa30-158">Not 0, and a valid code page.</span></span>|  
|<span data-ttu-id="faa30-159">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="faa30-159">DT_WSTR</span></span>|<span data-ttu-id="faa30-160">Maior que 0 e menor que 4.000.</span><span class="sxs-lookup"><span data-stu-id="faa30-160">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="faa30-161">0</span><span class="sxs-lookup"><span data-stu-id="faa30-161">0</span></span>|<span data-ttu-id="faa30-162">0</span><span class="sxs-lookup"><span data-stu-id="faa30-162">0</span></span>|<span data-ttu-id="faa30-163">0</span><span class="sxs-lookup"><span data-stu-id="faa30-163">0</span></span>|  
  
 <span data-ttu-id="faa30-164">Como as restrições nas propriedades de tipo de dados são baseadas no tipo de dados da coluna de saída, você deve escolher o tipo de dados correto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] quando trabalha com tipos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="faa30-164">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="faa30-165">A classe base fornece três métodos auxiliares, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, que auxiliam desenvolvedores de componente gerenciados a selecionar um tipo de dados do [!INCLUDE[ssIS](../../includes/ssis-md.md)] que recebeu um tipo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="faa30-165">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A> that assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="faa30-166">Esses métodos convertem tipos de dados gerenciados em tipos de dados do [!INCLUDE[ssIS](../../includes/ssis-md.md)] e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="faa30-166">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="faa30-167">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="faa30-167">Run Time</span></span>  
 <span data-ttu-id="faa30-168">Geralmente, a implementação da parte de tempo de execução do componente é categorizada em duas tarefas – localizar as colunas de entrada e saída do componente no buffer e ler ou escrever os valores dessas colunas nas linhas de entrada do buffer.</span><span class="sxs-lookup"><span data-stu-id="faa30-168">Generally, the implementation of the run-time part of the component is categorized into two tasks-locating the input and output columns of the component in the buffer, and reading or writing the values of these columns in the incoming buffer rows.</span></span>  
  
### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="faa30-169">Localizando colunas no buffer</span><span class="sxs-lookup"><span data-stu-id="faa30-169">Locating Columns in the Buffer</span></span>  
 <span data-ttu-id="faa30-170">O número de colunas nos buffers fornecido a um componente durante a execução provavelmente excederá o número de colunas nas coleções de entrada ou saída do componente.</span><span class="sxs-lookup"><span data-stu-id="faa30-170">The number of columns in the buffers that are provided to a component during execution will likely exceed the number of columns in the input or output collections of the component.</span></span> <span data-ttu-id="faa30-171">Isso se dá por que cada buffer contém todas as colunas de saída definidas nos componentes em um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="faa30-171">This is because each buffer contains all the output columns defined in the components in a data flow.</span></span> <span data-ttu-id="faa30-172">Para que as colunas do buffer sejam corretamente associadas às colunas da entrada ou da saída, os desenvolvedores de componentes devem usar o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="faa30-172">To ensure that the buffer columns are correctly matched to the columns of the input or output, component developers must use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="faa30-173">Esse método localiza uma coluna no buffer especificado por sua ID de linhagem.</span><span class="sxs-lookup"><span data-stu-id="faa30-173">This method locates a column in the specified buffer by its lineage ID.</span></span> <span data-ttu-id="faa30-174">Normalmente, são localizadas colunas durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> por que este é o primeiro método de tempo de execução em que a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> fica disponível.</span><span class="sxs-lookup"><span data-stu-id="faa30-174">Typically columns are located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> because this is the first run-time method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property becomes available.</span></span>  
  
 <span data-ttu-id="faa30-175">O exemplo de código seguinte mostra um componente que localiza índices das colunas em sua coleção de colunas de entrada e saída durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="faa30-175">The following code example shows a component that locates indexes of the columns in its input and output column collection during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span> <span data-ttu-id="faa30-176">Os índices da coluna são armazenados em uma matriz de inteiro e podem ser acessados pelo componente durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="faa30-176">The column indexes are stored in an integer array, and can be accessed by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
```csharp  
int []inputColumns;  
int []outputColumns;  
  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];  
  
    inputColumns = new int[input.InputColumnCollection.Count];  
    outputColumns = new int[output.OutputColumnCollection.Count];  
  
    for(int col=0; col < input.InputColumnCollection.Count; col++)  
    {  
        IDTSInputColumn100 inputColumn = input.InputColumnCollection[col];  
        inputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID);  
    }  
  
    for(int col=0; col < output.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 outputColumn = output.OutputColumnCollection[col];  
        outputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID);  
    }  
  
}  
```  
  
```vb  
Public Overrides Sub PreExecute()  
  
    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)  
  
    ReDim inputColumns(input.InputColumnCollection.Count)  
    ReDim outputColumns(output.OutputColumnCollection.Count)  
  
    For col As Integer = 0 To input.InputColumnCollection.Count  
  
        Dim inputColumn As IDTSInputColumn100 = input.InputColumnCollection(col)  
        inputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID)  
    Next  
  
    For col As Integer = 0 To output.OutputColumnCollection.Count  
  
        Dim outputColumn As IDTSOutputColumn100 = output.OutputColumnCollection(col)  
        outputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID)  
    Next  
  
End Sub  
```  
  
### <a name="processing-rows"></a><span data-ttu-id="faa30-177">Processando linhas</span><span class="sxs-lookup"><span data-stu-id="faa30-177">Processing Rows</span></span>  
 <span data-ttu-id="faa30-178">Componentes recebem objetos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> que contêm linhas e colunas no método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="faa30-178">Components receive <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain rows and columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="faa30-179">Durante esse método são iteradas as linhas do buffer e as colunas identificadas durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> são lidas e modificadas.</span><span class="sxs-lookup"><span data-stu-id="faa30-179">During this method the rows in the buffer are iterated, and the columns identified during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> are read and modified.</span></span> <span data-ttu-id="faa30-180">O método é chamado repetidamente pela tarefa de fluxo de dados até que nenhuma linha seja mais fornecida a partir do componente upstream.</span><span class="sxs-lookup"><span data-stu-id="faa30-180">The method is called repeatedly by the data flow task until no more rows are provided from the upstream component.</span></span>  
  
 <span data-ttu-id="faa30-181">Uma coluna individual no buffer é lida ou gravada através do método de acesso do indexador matriz ou um dos métodos `Get` ou `Set`.</span><span class="sxs-lookup"><span data-stu-id="faa30-181">An individual column in the buffer is read or written by using the array indexer access method, or by using one of the `Get` or `Set` methods.</span></span> <span data-ttu-id="faa30-182">Os métodos `Get` e `Set` são mais eficientes e devem ser usados quando o tipo de dados da coluna no buffer for conhecido.</span><span class="sxs-lookup"><span data-stu-id="faa30-182">The `Get` and `Set` methods are more efficient and should be used when the data type of the column in the buffer is known.</span></span>  
  
 <span data-ttu-id="faa30-183">O exemplo de código seguinte mostra uma implementação do método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> que processa linhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="faa30-183">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method that processes incoming rows.</span></span>  
  
```csharp  
public override void ProcessInput( int InputID, PipelineBuffer buffer)  
{  
       while( buffer.NextRow())  
       {  
            for(int x=0; x < inputColumns.Length;x++)  
            {  
                if(!buffer.IsNull(inputColumns[x]))  
                {  
                    object columnData = buffer[inputColumns[x]];  
                    // TODO: Modify the column data.  
                    buffer[inputColumns[x]] = columnData;  
                }  
            }  
  
      }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal InputID As Integer, ByVal buffer As PipelineBuffer)  
  
        While (buffer.NextRow())  
  
            For x As Integer = 0 To inputColumns.Length  
  
                if buffer.IsNull(inputColumns(x)) = false then  
  
                    Dim columnData As Object = buffer(inputColumns(x))  
                    ' TODO: Modify the column data.  
                    buffer(inputColumns(x)) = columnData  
  
                End If  
            Next  
  
        End While  
End Sub  
```  
  
## <a name="sample"></a><span data-ttu-id="faa30-184">Amostra</span><span class="sxs-lookup"><span data-stu-id="faa30-184">Sample</span></span>  
 <span data-ttu-id="faa30-185">O exemplo seguinte mostra um componente de transformação simples com saídas síncronas que converte os valores de todas as colunas de cadeia de caracteres para escrever em letra maiúscula.</span><span class="sxs-lookup"><span data-stu-id="faa30-185">The following sample shows a simple transformation component with synchronous outputs that converts the values of all string columns to uppercase.</span></span> <span data-ttu-id="faa30-186">Esse exemplo não demonstra todos os métodos e todas as funcionalidades discutidas nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="faa30-186">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="faa30-187">Ele demonstra os métodos importantes que todo componente de transformação personalizado com saídas síncronas deve substituir, mas não contém código para a validação em tempo de design.</span><span class="sxs-lookup"><span data-stu-id="faa30-187">It demonstrates the important methods that every custom transformation component with synchronous outputs must override, but does not contain code for design-time validation.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
  
namespace Uppercase  
{  
  [DtsPipelineComponent(DisplayName = "Uppercase")]  
  public class Uppercase : PipelineComponent  
  {  
    ArrayList m_ColumnIndexList = new ArrayList();  
  
    public override void ProvideComponentProperties()  
    {  
      base.ProvideComponentProperties();  
      ComponentMetaData.InputCollection[0].Name = "Uppercase Input";  
      ComponentMetaData.OutputCollection[0].Name = "Uppercase Output";  
    }  
  
    public override void PreExecute()  
    {  
      IDTSInput100 input = ComponentMetaData.InputCollection[0];  
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;  
  
      foreach (IDTSInputColumn100 column in inputColumns)  
      {  
        if (column.DataType == DataType.DT_STR || column.DataType == DataType.DT_WSTR)  
        {  
          m_ColumnIndexList.Add((int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID));  
        }  
      }  
    }  
  
    public override void ProcessInput(int inputID, PipelineBuffer buffer)  
    {  
      while (buffer.NextRow())  
      {  
        foreach (int columnIndex in m_ColumnIndexList)  
        {  
          string str = buffer.GetString(columnIndex);  
          buffer.SetString(columnIndex, str.ToUpper());  
        }  
      }  
    }  
  }  
}  
```  
  
```vb  
Imports System   
Imports System.Collections   
Imports Microsoft.SqlServer.Dts.Pipeline   
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper   
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper   
Namespace Uppercase   
  
 <DtsPipelineComponent(DisplayName="Uppercase")> _   
 Public Class Uppercase   
 Inherits PipelineComponent   
   Private m_ColumnIndexList As ArrayList = New ArrayList   
  
   Public  Overrides Sub ProvideComponentProperties()   
     MyBase.ProvideComponentProperties   
     ComponentMetaData.InputCollection(0).Name = "Uppercase Input"   
     ComponentMetaData.OutputCollection(0).Name = "Uppercase Output"   
   End Sub   
  
   Public  Overrides Sub PreExecute()   
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection   
     For Each column As IDTSInputColumn100 In inputColumns   
       If column.DataType = DataType.DT_STR OrElse column.DataType = DataType.DT_WSTR Then   
         m_ColumnIndexList.Add(CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer))   
       End If   
     Next   
   End Sub   
  
   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
     While buffer.NextRow   
       For Each columnIndex As Integer In m_ColumnIndexList   
         Dim str As String = buffer.GetString(columnIndex)   
         buffer.SetString(columnIndex, str.ToUpper)   
       Next   
     End While   
   End Sub   
 End Class   
End Namespace  
```  
  
<span data-ttu-id="faa30-188">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="faa30-188">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="faa30-189">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="faa30-189">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="faa30-190">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="faa30-190">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="faa30-191">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="faa30-191">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa30-192">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="faa30-192">See Also</span></span>  
 <span data-ttu-id="faa30-193">[Desenvolvendo um componente de transformação personalizado com saídas assíncronas](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span><span class="sxs-lookup"><span data-stu-id="faa30-193">[Developing a Custom Transformation Component with Asynchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span></span>  
 <span data-ttu-id="faa30-194">[Noções básicas sobre transformações síncronas e assíncronas](../understanding-synchronous-and-asynchronous-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="faa30-194">[Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) </span></span>  
 [<span data-ttu-id="faa30-195">Criando uma transformação síncrona com o componente Script</span><span class="sxs-lookup"><span data-stu-id="faa30-195">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
