---
title: Desenvolvendo um componente de destino personalizado | Microsoft Docs
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
- validation [Integration Services], components
- destinations [Integration Services], components
- ProcessInput method
- external data sources [Integration Services]
- custom data flow components [Integration Services], destination components
- data flow components [Integration Services], destination components
ms.assetid: 24619363-9535-4c0e-8b62-1d22c6630e40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6979d14afa0490638162c35bb660f15506803484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678264"
---
# <a name="developing-a-custom-destination-component"></a><span data-ttu-id="d3e23-102">Desenvolvendo um componente de destino personalizado</span><span class="sxs-lookup"><span data-stu-id="d3e23-102">Developing a Custom Destination Component</span></span>
  <span data-ttu-id="d3e23-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] permite que os desenvolvedores escrevam componentes de destino personalizados que podem se conectar aos dados e armazená-los em qualquer fonte de dados personalizada.</span><span class="sxs-lookup"><span data-stu-id="d3e23-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write custom destination components that can connect to and store data in any custom data source.</span></span> <span data-ttu-id="d3e23-104">Os componentes de destino personalizados são úteis quando você precisa se conectar a fontes de dados que não podem ser acessadas através de um dos componentes de origem existentes incluídos no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3e23-104">Custom destination components are useful when you need to connect to data sources that cannot be accessed by using one of the existing source components included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="d3e23-105">Os componentes de destino têm uma ou mais entradas e zero saídas.</span><span class="sxs-lookup"><span data-stu-id="d3e23-105">Destination components have one or more inputs and zero outputs.</span></span> <span data-ttu-id="d3e23-106">Em tempo de design, eles criam e configuram conexões e metadados de coluna de leitura a partir da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-106">At design time, they create and configure connections and read column metadata from the external data source.</span></span> <span data-ttu-id="d3e23-107">Durante a execução, eles se conectam à fonte de dados externa e adicionam linhas que são recebidas dos componentes upstream do fluxo de dados para a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-107">During execution, they connect to their external data source and add rows that are received from the components upstream in the data flow to the external data source.</span></span> <span data-ttu-id="d3e23-108">Se a fonte de dados externa existir antes da execução do componente, o componente de destino também deverá verificar se os tipos de dados das colunas recebidas pelo componente coincidem com os tipos de dados das colunas da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-108">If the external data source exists prior to execution of the component, the destination component must also ensure that the data types of the columns that the component receives match the data types of the columns at the external data source.</span></span>

 <span data-ttu-id="d3e23-109">Essa seção discute os detalhes de como desenvolver componentes de destino e fornece exemplos de código para esclarecer conceitos importantes.</span><span class="sxs-lookup"><span data-stu-id="d3e23-109">This section discusses the details of how to develop destination components, and provides code examples to clarify important concepts.</span></span> <span data-ttu-id="d3e23-110">Para obter uma visão geral do desenvolvimento de componentes de fluxo de dados, consulte [Desenvolvendo um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d3e23-110">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="d3e23-111">Tempo de design</span><span class="sxs-lookup"><span data-stu-id="d3e23-111">Design Time</span></span>
 <span data-ttu-id="d3e23-112">A implementação da funcionalidade em tempo de design de um componente de destino envolve a especificação de uma conexão a uma fonte de dados externa e a confirmação de que o componente foi configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="d3e23-112">Implementing the design-time functionality of a destination component involves specifying a connection to an external data source and validating that the component has been correctly configured.</span></span> <span data-ttu-id="d3e23-113">Por definição, um componente de destino tem uma entrada e possivelmente uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="d3e23-113">By definition, a destination component has one input and possibly one error output.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="d3e23-114">Criando o componente</span><span class="sxs-lookup"><span data-stu-id="d3e23-114">Creating the Component</span></span>
 <span data-ttu-id="d3e23-115">Os componentes de destino se conectam a fontes de dados externas através de objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> definidos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="d3e23-115">Destination components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="d3e23-116">O componente de destino indica seu requisito de um gerenciador de conexões para o Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] e para usuários do componente, adicionando um elemento à coleção <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-116">The destination component indicates its requirement for a connection manager to the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, and to users of the component, by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span></span> <span data-ttu-id="d3e23-117">Essa coleção tem duas finalidades: primeiro, ela transmite a necessidade de um gerenciador de conexões para o Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)]; segundo, depois de o usuário selecionar ou criar um gerenciador de conexões, ele mantém uma referência a esse gerenciador no pacote em uso pelo componente.</span><span class="sxs-lookup"><span data-stu-id="d3e23-117">This collection serves two purposes: first, it advertises the need for a connection manager to [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer; then, after the user has selected or created a connection manager, it holds a reference to the connection manager in the package that is being used by the component.</span></span> <span data-ttu-id="d3e23-118">Quando um <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> é adicionado à coleção, o **Editor Avançado** exibe a guia **Propriedades da Conexão** para solicitar que o usuário selecione ou crie uma conexão no pacote a ser usado pelo componente.</span><span class="sxs-lookup"><span data-stu-id="d3e23-118">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> is added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, to prompt the user to select or create a connection in the package for use by the component.</span></span>

 <span data-ttu-id="d3e23-119">O exemplo de código a seguir mostra uma implementação do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> que adiciona uma entrada e, depois, um objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> ao <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-119">The following code sample shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an input, and then adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "Destination Component",ComponentType =ComponentType.DestinationAdapter)]
    public class DestinationComponent : PipelineComponent 
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSInput100 input = ComponentMetaData.InputCollection.New();
            input.Name = "Input";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.net";
        }
    }
}
```

```vb
Imports System
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="Destination Component", ComponentType:=ComponentType.DestinationAdapter)> _
    Public Class DestinationComponent
        Inherits PipelineComponent

        Public Overrides Sub ProvideComponentProperties()

            ' Reset the component.
            Me.RemoveAllInputsOutputsAndCustomProperties()
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()
            input.Name = "Input"

            Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
            connection.Name = "ADO.net"

        End Sub
    End Class
End Namespace
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="d3e23-120">Conectando-se a uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="d3e23-120">Connecting to an External Data Source</span></span>
 <span data-ttu-id="d3e23-121">Depois da adição de uma conexão ao <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> para estabelecer uma conexão à fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-121">After a connection is added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="d3e23-122">Esse método é chamado em tempo de design e em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d3e23-122">This method is called at design time and at run time.</span></span> <span data-ttu-id="d3e23-123">O componente deve estabelecer uma conexão com o gerenciador de conexões especificado pela conexão em tempo de execução e, depois, com a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-123">The component must establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span> <span data-ttu-id="d3e23-124">Depois de concluir essas conexões, o componente deverá armazenar a conexão em cache internamente e liberá-la quando o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> for chamado.</span><span class="sxs-lookup"><span data-stu-id="d3e23-124">Once established, the component should cache the connection internally and release it when <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> is called.</span></span> <span data-ttu-id="d3e23-125">Os desenvolvedores substituem esse método e liberam a conexão estabelecida pelo componente durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="d3e23-126">Esses dois métodos, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, são chamados em tempo de design e em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d3e23-126">Both of these methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, are called at design time and at run time.</span></span>

 <span data-ttu-id="d3e23-127">O exemplo de código a seguir mostra um componente que se conecta a uma conexão ADO.NET no método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> e, depois, fecha a conexão no <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-127">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method, and then closes the connection in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

private SqlConnection sqlConnection;

public override void AcquireConnections(object transaction)
{
    if (ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager != null)
    {
        ConnectionManager cm = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager);
        ConnectionManagerAdoNet cmado = cm.InnerObject as ConnectionManagerAdoNet;

        if (cmado == null)
            throw new Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.");

        sqlConnection = cmado.AcquireConnection(transaction) as SqlConnection;
        sqlConnection.Open();
    }
}

public override void ReleaseConnections()
{
    if (sqlConnection != null && sqlConnection.State != ConnectionState.Closed)
        sqlConnection.Close();
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) = False Then

        Dim cm As ConnectionManager = DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject,ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If IsNothing(sqlConnection) = False And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="d3e23-128">Validando o componente</span><span class="sxs-lookup"><span data-stu-id="d3e23-128">Validating the Component</span></span>
 <span data-ttu-id="d3e23-129">Os desenvolvedores de componentes de destino devem executar a validação conforme descrito em [Validação de Componente](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d3e23-129">Destination component developers should perform validation as described in [Component Validation](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span> <span data-ttu-id="d3e23-130">Além disso, eles devem verificar se as propriedades do tipo de dados das colunas definidas na coleção de colunas de entrada do componente coincidem com as das colunas da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-130">In addition, they should verify that the data type properties of the columns defined in the component's input column collection match the columns at the external data source.</span></span> <span data-ttu-id="d3e23-131">Às vezes, a verificação de colunas de entrada em relação à fonte de dados externa pode ser impossível ou indesejável. Isso ocorre, por exemplo, quando o componente ou o Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] se encontra desconectado ou quando viagens de ida e volta ao servidor são inaceitáveis.</span><span class="sxs-lookup"><span data-stu-id="d3e23-131">At times, verifying the input columns against the external data source can be impossible or undesirable, such as when the component or the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is in a disconnected state, or when round trips to the server are not acceptable.</span></span> <span data-ttu-id="d3e23-132">Nessas situações, as colunas da coleção de colunas de entrada podem ser validadas através do objeto de entrada <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-132">In these situations, the columns in the input column collection can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> of the input object.</span></span>

 <span data-ttu-id="d3e23-133">Essa coleção existe nos objetos de entrada e saída e precisa ser preenchida pelo desenvolvedor de componentes a partir das colunas da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-133">This collection exists on both input and output objects and must be populated by the component developer from the columns at the external data source.</span></span> <span data-ttu-id="d3e23-134">Essa coleção pode ser usada para validar as colunas de entrada quando o Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] está offline, quando o componente está desconectado ou quando a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> é `false`.</span><span class="sxs-lookup"><span data-stu-id="d3e23-134">This collection can be used to validate the input columns when the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>

 <span data-ttu-id="d3e23-135">O código de exemplo a seguir adiciona uma coluna de metadados externa com base em uma coluna de entrada existente.</span><span class="sxs-lookup"><span data-stu-id="d3e23-135">The following sample code adds an external metadata column based on an existing input column.</span></span>

```csharp
private void AddExternalMetaDataColumn(IDTSInput100 input,IDTSInputColumn100 inputColumn)
{
    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = input.ExternalMetadataColumnCollection.New();
    externalColumn.Name = inputColumn.Name;
    externalColumn.Precision = inputColumn.Precision;
    externalColumn.Length = inputColumn.Length;
    externalColumn.DataType = inputColumn.DataType;
    externalColumn.Scale = inputColumn.Scale;

    // Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID;
}
```

```vb
Private Sub AddExternalMetaDataColumn(ByVal input As IDTSInput100, ByVal inputColumn As IDTSInputColumn100)

    ' Set the properties of the external metadata column.
    Dim externalColumn As IDTSExternalMetadataColumn100 = input.ExternalMetadataColumnCollection.New()
    externalColumn.Name = inputColumn.Name
    externalColumn.Precision = inputColumn.Precision
    externalColumn.Length = inputColumn.Length
    externalColumn.DataType = inputColumn.DataType
    externalColumn.Scale = inputColumn.Scale

    ' Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID

End Sub
```

## <a name="run-time"></a><span data-ttu-id="d3e23-136">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="d3e23-136">Run Time</span></span>
 <span data-ttu-id="d3e23-137">Durante a execução, o componente de destino recebe uma chamada para o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> toda vez que um <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> completo é disponibilizado do componente upstream.</span><span class="sxs-lookup"><span data-stu-id="d3e23-137">During execution, the destination component receives a call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method each time a full <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> is available from the upstream component.</span></span> <span data-ttu-id="d3e23-138">Esse método será chamado repetidamente até não haver mais buffers disponíveis e a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> ser `true`.</span><span class="sxs-lookup"><span data-stu-id="d3e23-138">This method is called repeatedly until there are no more buffers available and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="d3e23-139">Durante esse método, os componentes de destino fazem a leitura de colunas e linhas no buffer e as adicionam à fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-139">During this method, destination components read columns and rows in the buffer, and add them to the external data source.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="d3e23-140">Localizando colunas no buffer</span><span class="sxs-lookup"><span data-stu-id="d3e23-140">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="d3e23-141">O buffer de entrada de um componente contém todas as colunas definidas nas coleções de colunas de saída dos componentes upstream a partir do componente no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="d3e23-141">The input buffer for a component contains all the columns defined in the output column collections of the components upstream from the component in the data flow.</span></span> <span data-ttu-id="d3e23-142">Por exemplo, se um componente de origem fornecer três colunas na saída e o próximo componente adicionar mais uma coluna de saída, o buffer fornecido ao componente de destino conterá quatro colunas, mesmo que o componente de destino só grave duas colunas.</span><span class="sxs-lookup"><span data-stu-id="d3e23-142">For example, if a source component provides three columns in its output, and the next component adds an additional output column, the buffer provided to the destination component contains four columns, even if the destination component will write only two columns.</span></span>

 <span data-ttu-id="d3e23-143">A ordem das colunas no buffer de entrada não é definida pelo índice da coluna na coleção de colunas de entrada do componente de destino.</span><span class="sxs-lookup"><span data-stu-id="d3e23-143">The order of the columns in the input buffer is not defined by the index of the column in the input column collection of the destination component.</span></span> <span data-ttu-id="d3e23-144">É possível localizar de forma confiável colunas em uma linha de buffer através do método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-144">Columns can be reliably located in a buffer row only by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="d3e23-145">Esse método localiza a coluna que tem a ID de linhagem especificada no buffer especificado e retorna sua localização na linha.</span><span class="sxs-lookup"><span data-stu-id="d3e23-145">This method locates the column that has the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="d3e23-146">Os índices das colunas de entrada costumam ser localizados durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> e são armazenados em cache pelo desenvolvedor para uso posterior durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-146">The indexes of the input columns are typically located during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and cached by the developer for use later during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>

 <span data-ttu-id="d3e23-147">O exemplo de código a seguir indica a localização das colunas de entrada no buffer durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> e armazena-as em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d3e23-147">The following code example finds the location of the input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> and stores them in an array.</span></span> <span data-ttu-id="d3e23-148">A matriz é usada subsequentemente durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> para ler os valores das colunas no buffer.</span><span class="sxs-lookup"><span data-stu-id="d3e23-148">The array is subsequently used during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> to read the values of the columns in the buffer.</span></span>

```csharp
int[] cols;

public override void PreExecute()
{
    IDTSInput100 input = ComponentMetaData.InputCollection[0];

    cols = new int[input.InputColumnCollection.Count];

    for (int x = 0; x < input.InputColumnCollection.Count; x++)
    {
        cols[x] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[x].LineageID);
    }
}
```

```vb
Private cols As Integer()

Public Overrides Sub PreExecute()

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)

    ReDim cols(input.InputColumnCollection.Count)

    For x As Integer = 0 To input.InputColumnCollection.Count

        cols(x) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(x).LineageID)
    Next x

End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="d3e23-149">Processando linhas</span><span class="sxs-lookup"><span data-stu-id="d3e23-149">Processing Rows</span></span>
 <span data-ttu-id="d3e23-150">Depois de serem localizadas, as colunas de entrada no buffer podem ser lidas e escritas na fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="d3e23-150">Once the input columns have been located in the buffer, they can be read and written to the external data source.</span></span>

 <span data-ttu-id="d3e23-151">Apesar de o componente de destino escrever linhas na fonte de dados externa, talvez você queira atualizar o contador de desempenho "Linhas lidas" ou "Bytes de BLOB lidos", chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-151">While the destination component writes rows to the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="d3e23-152">Para obter mais informações, consulte [Performance Counters](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="d3e23-152">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="d3e23-153">O exemplo a seguir mostra um componente que lê linhas do buffer fornecido em <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e23-153">The following example shows a component that reads rows from the buffer provided in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="d3e23-154">Os índices das colunas no buffer foram localizados durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> no exemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="d3e23-154">The indexes of the columns in the buffer were located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the preceding code example.</span></span>

```csharp
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
        while (buffer.NextRow())
        {
            foreach (int col in cols)
            {
                if (!buffer.IsNull(col))
                {
                    //  TODO: Read the column data.
                }
            }
        }
}
```

```vb
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

        While (buffer.NextRow())

            For Each col As Integer In cols

                If buffer.IsNull(col) = False Then

                    '  TODO: Read the column data.
                End If

            Next col
        End While
End Sub
```

## <a name="sample"></a><span data-ttu-id="d3e23-155">Amostra</span><span class="sxs-lookup"><span data-stu-id="d3e23-155">Sample</span></span>
 <span data-ttu-id="d3e23-156">O exemplo a seguir mostra um componente de destino simples que usa um gerenciador de conexões do Arquivo para salvar dados binários do fluxo de dados em arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3e23-156">The following sample shows a simple destination component that uses a File connection manager to save binary data from the data flow into files.</span></span> <span data-ttu-id="d3e23-157">Esse exemplo não demonstra todos os métodos e todas as funcionalidades discutidas nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="d3e23-157">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="d3e23-158">Ele demonstra os métodos importantes que todo componente de destino personalizado deve substituir, mas não contém código para a validação em tempo de design.</span><span class="sxs-lookup"><span data-stu-id="d3e23-158">It demonstrates the important methods that every custom destination component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace BlobDst
{
  [DtsPipelineComponent(DisplayName = "BLOB Extractor Destination", Description = "Writes values of BLOB columns to files")]
  public class BlobDst : PipelineComponent
  {
    string m_DestDir;
    int m_FileNameColumnIndex = -1;
    int m_BlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection.New();
      input.Name = "BLOB Extractor Destination Input";
      input.HasSideEffects = true;

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_DestDir = (string)conn.ConnectionManager.AcquireConnection(null);

      if (m_DestDir.Length > 0 && m_DestDir[m_DestDir.Length - 1] != '\\')
        m_DestDir += "\\";
    }

    public override IDTSInputColumn100 SetUsageType(int inputID, IDTSVirtualInput100 virtualInput, int lineageID, DTSUsageType usageType)
    {
      IDTSInputColumn100 inputColumn = base.SetUsageType(inputID, virtualInput, lineageID, usageType);
      IDTSCustomProperty100 custProp;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsFileName";
      custProp.Value = (object)false;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsBLOB";
      custProp.Value = (object)false;

      return inputColumn;
    }

    public override void PreExecute()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection[0];
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;
      IDTSCustomProperty100 custProp;

      foreach (IDTSInputColumn100 column in inputColumns)
      {
        custProp = column.CustomPropertyCollection["IsFileName"];
        if ((bool)custProp.Value == true)
        {
          m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }

        custProp = column.CustomPropertyCollection["IsBLOB"];
        if ((bool)custProp.Value == true)
        {
          m_BlobColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }
      }
    }

    public override void ProcessInput(int inputID, PipelineBuffer buffer)
    {
      while (buffer.NextRow())
      {
        string strFileName = buffer.GetString(m_FileNameColumnIndex);
        int blobLength = (int)buffer.GetBlobLength(m_BlobColumnIndex);
        byte[] blobData = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength);

        strFileName = TranslateFileName(strFileName);

        // Make sure directory exists before creating file.
        FileInfo fi = new FileInfo(strFileName);
        if (!fi.Directory.Exists)
          fi.Directory.Create();

        // Write the data to the file.
        FileStream fs = new FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None);
        fs.Write(blobData, 0, blobLength);
        fs.Close();
      }
    }

    private string TranslateFileName(string fileName)
    {
      if (fileName.Length > 2 && fileName[1] == ':')
        return m_DestDir + fileName.Substring(3, fileName.Length - 3);
      else
        return m_DestDir + fileName;
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Namespace BlobDst 

 <DtsPipelineComponent(DisplayName="BLOB Extractor Destination", Description="Writes values of BLOB columns to files")> _ 
 Public Class BlobDst 
 Inherits PipelineComponent 
   Private m_DestDir As String 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_BlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New 
     input.Name = "BLOB Extractor Destination Input" 
     input.HasSideEffects = True 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_DestDir = CType(conn.ConnectionManager.AcquireConnection(Nothing), String) 
     If m_DestDir.Length > 0 AndAlso Not (m_DestDir(m_DestDir.Length - 1) = "\"C) Then 
       m_DestDir += "\" 
     End If 
   End Sub 

   Public  Overrides Function SetUsageType(ByVal inputID As Integer, ByVal virtualInput As IDTSVirtualInput100, ByVal lineageID As Integer, ByVal usageType As DTSUsageType) As IDTSInputColumn100 
     Dim inputColumn As IDTSInputColumn100 = MyBase.SetUsageType(inputID, virtualInput, lineageID, usageType) 
     Dim custProp As IDTSCustomProperty100 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsFileName" 
     custProp.Value = CType(False, Object) 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsBLOB" 
     custProp.Value = CType(False, Object) 
     Return inputColumn 
   End Function 

   Public  Overrides Sub PreExecute() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0) 
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection 
     Dim custProp As IDTSCustomProperty100 
     For Each column As IDTSInputColumn100 In inputColumns 
       custProp = column.CustomPropertyCollection("IsFileName") 
       If CType(custProp.Value, Boolean) = True Then 
         m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
       custProp = column.CustomPropertyCollection("IsBLOB") 
       If CType(custProp.Value, Boolean) = True Then 
         m_BlobColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
     Next 
   End Sub 

   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
     While buffer.NextRow 
       Dim strFileName As String = buffer.GetString(m_FileNameColumnIndex) 
       Dim blobLength As Integer = CType(buffer.GetBlobLength(m_BlobColumnIndex), Integer) 
       Dim blobData As Byte() = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength) 
       strFileName = TranslateFileName(strFileName) 
       Dim fi As FileInfo = New FileInfo(strFileName) 
       ' Make sure directory exists before creating file.
       If Not fi.Directory.Exists Then 
         fi.Directory.Create 
       End If 
       ' Write the data to the file.
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None) 
       fs.Write(blobData, 0, blobLength) 
       fs.Close 
     End While 
   End Sub 

   Private Function TranslateFileName(ByVal fileName As String) As String 
     If fileName.Length > 2 AndAlso fileName(1) = ":"C Then 
       Return m_DestDir + fileName.Substring(3, fileName.Length - 3) 
     Else 
       Return m_DestDir + fileName 
     End If 
   End Function 
 End Class 
End Namespace
```

<span data-ttu-id="d3e23-159">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d3e23-159">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d3e23-160">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="d3e23-160">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d3e23-161">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="d3e23-161">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d3e23-162">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="d3e23-162">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3e23-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3e23-163">See Also</span></span>
 <span data-ttu-id="d3e23-164">[Desenvolvendo um componente de origem personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [criando um destino com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="d3e23-164">[Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span></span>


