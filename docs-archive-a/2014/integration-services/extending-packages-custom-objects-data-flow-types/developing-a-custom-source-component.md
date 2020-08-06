---
title: Desenvolvendo um componente de origem personalizado | Microsoft Docs
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
- validation [Integration Services], components
- external data sources [Integration Services]
- data flow components [Integration Services], source components
- output columns [Integration Services]
- custom data flow components [Integration Services], source components
- custom sources [Integration Services]
- source components [Integration Services]
ms.assetid: 4dc0f631-8fd6-4007-b573-ca67f58ca068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6679b28463a09efe069235a5aef9dca54a381d62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683627"
---
# <a name="developing-a-custom-source-component"></a><span data-ttu-id="2e040-102">Desenvolvendo um componente de fonte personalizado</span><span class="sxs-lookup"><span data-stu-id="2e040-102">Developing a Custom Source Component</span></span>
  <span data-ttu-id="2e040-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] habilita desenvolvedores a escrever componentes de origem que podem ser conectados a fontes de dados personalizadas e fornecer dados dessas fontes a outros componentes em uma tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="2e040-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write source components that can connect to custom data sources and supply data from those sources to other components in a data flow task.</span></span> <span data-ttu-id="2e040-104">A capacidade de criar fontes personalizadas é valiosa quando você precisa se conectar a fontes de dados que não podem ser acessadas através de uma das fontes existentes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e040-104">The ability to create custom sources is valuable when you must connect to data sources that cannot be accessed by using one of the existing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources.</span></span>

 <span data-ttu-id="2e040-105">Componentes de origem têm uma ou mais saídas e zero entradas.</span><span class="sxs-lookup"><span data-stu-id="2e040-105">Source components have one or more outputs and zero inputs.</span></span> <span data-ttu-id="2e040-106">Em tempo de design, os componentes de origem são usados para criar e configurar conexões, ler metadados de colunas a partir da fonte de dados externa e configurar as colunas da saída da origem com base na fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="2e040-106">At design time, source components are used to create and configure connections, read column metadata from the external data source, and configure the source's output columns based on the external data source.</span></span> <span data-ttu-id="2e040-107">Durante a execução, eles se conectam à fonte de dados externa e adicionam linhas a um buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="2e040-107">During execution they connect to the external data source and add rows to an output buffer.</span></span> <span data-ttu-id="2e040-108">A tarefa de fluxo de dados fornece esse buffer de linhas de dados a componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="2e040-108">The data flow task then provides this buffer of data rows to downstream components.</span></span>

 <span data-ttu-id="2e040-109">Para obter uma visão geral do desenvolvimento de componentes de fluxo de dados, consulte [Desenvolvendo um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2e040-109">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="2e040-110">Tempo de design</span><span class="sxs-lookup"><span data-stu-id="2e040-110">Design Time</span></span>
 <span data-ttu-id="2e040-111">A implementação da funcionalidade em tempo de design de um componente de origem envolve a especificação de uma conexão a uma fonte de dados externa, a adição e configuração de colunas de saída que refletem a fonte dados, e a confirmação de que o componente está pronto para execução.</span><span class="sxs-lookup"><span data-stu-id="2e040-111">Implementing the design-time functionality of a source component involves specifying a connection to an external data source, adding and configuring output columns that reflect the data source, and validating that the component is ready to execute.</span></span> <span data-ttu-id="2e040-112">Por definição, um componente de origem tem zero entradas e uma ou mais saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="2e040-112">By definition, a source component has zero inputs and one or more asynchronous outputs.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="2e040-113">Criando o componente</span><span class="sxs-lookup"><span data-stu-id="2e040-113">Creating the Component</span></span>
 <span data-ttu-id="2e040-114">Os componentes de origem se conectam a fontes de dados externas através de objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> definidos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="2e040-114">Source components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="2e040-115">Eles indicam o seu requisito para um gerenciador de conexões por meio da adição de um elemento à coleção <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-115">They indicate their requirement for a connection manager by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="2e040-116">Essa coleção tem duas finalidades: manter referências a gerenciadores de conexões no pacote usado pelo componente e divulgar a necessidade de um gerenciador de conexões para o designer.</span><span class="sxs-lookup"><span data-stu-id="2e040-116">This collection serves two purposes-to hold references to connection managers in the package used by the component, and to advertise the need for a connection manager to the designer.</span></span> <span data-ttu-id="2e040-117">Quando um <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> é adicionado à coleção, o **Editor Avançado** exibe a guia **Propriedades da Conexão** que permite aos usuários selecionar ou criar uma conexão no pacote.</span><span class="sxs-lookup"><span data-stu-id="2e040-117">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> has been added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, which lets users select or create a connection in the package.</span></span>

 <span data-ttu-id="2e040-118">O exemplo de código a seguir mostra uma implementação de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> que adiciona uma saída e um objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> ao <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an output, and adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using System.Collections;
using System.Data;
using System.Data.SqlClient;
using System.Data.OleDb;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "MySourceComponent",ComponentType = ComponentType.SourceAdapter)]
    public class MyComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
            output.Name = "Output";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.NET";
        }
```

```vb
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Runtime
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper

<DtsPipelineComponent(DisplayName:="MySourceComponent", ComponentType:=ComponentType.SourceAdapter)> _
Public Class MySourceComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Allow for resetting the component.
        RemoveAllInputsOutputsAndCustomProperties()
        ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()
        output.Name = "Output"

        Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
        connection.Name = "ADO.NET"

    End Sub
End Class
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="2e040-119">Conectando-se a uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="2e040-119">Connecting to an External Data Source</span></span>
 <span data-ttu-id="2e040-120">Depois da adição de uma conexão ao <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> para estabelecer uma conexão à fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="2e040-120">After a connection has been added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="2e040-121">Esse método é chamado durante o tempo de design e execução.</span><span class="sxs-lookup"><span data-stu-id="2e040-121">This method is called during both design and execution time.</span></span> <span data-ttu-id="2e040-122">O componente deve estabelecer uma conexão com o gerenciador de conexões especificado pela conexão em tempo de execução e, depois, com a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="2e040-122">The component should establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span>

 <span data-ttu-id="2e040-123">Depois de estabelecida, a conexão deve ser armazenada em cache interiormente pelo componente e liberada quando o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> é chamado.</span><span class="sxs-lookup"><span data-stu-id="2e040-123">After the connection is established, it should be cached internally by the component and released when the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called.</span></span> <span data-ttu-id="2e040-124">O método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> é chamado em tempo de design e execução, como o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-124">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called at design and execution time, like the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method.</span></span> <span data-ttu-id="2e040-125">Os desenvolvedores substituem esse método e liberam a conexão estabelecida pelo componente durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span>

 <span data-ttu-id="2e040-126">O exemplo de código a seguir mostra um componente que se conecta a uma conexão ADO.NET no método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> e fecha a conexão no método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-126">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method and closes the connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method.</span></span>

```csharp
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
Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If Not IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) Then

        Dim cm As ConnectionManager = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject, ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If Not IsNothing(sqlConnection) And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="2e040-127">Criando e configurando colunas de saída</span><span class="sxs-lookup"><span data-stu-id="2e040-127">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="2e040-128">As colunas de saída de um componente de origem refletem colunas da fonte de dados externa que o componente adiciona ao fluxo de dados durante a execução.</span><span class="sxs-lookup"><span data-stu-id="2e040-128">The output columns of a source component reflect the columns from the external data source that the component adds to the data flow during execution.</span></span> <span data-ttu-id="2e040-129">Em tempo de design, você adiciona colunas de saída depois da configuração do componente para se conectar a uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="2e040-129">At design time, you add output columns after the component has been configured to connect to an external data source.</span></span> <span data-ttu-id="2e040-130">O método em tempo de design que um componente usa para adicionar as colunas à sua coleção de saídas varia de acordo com as necessidades do componente, embora elas não devam ser adicionadas durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> ou o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-130">The design-time method that a component uses to add the columns to its output collection can vary based on the needs of the component, although they should not be added during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="2e040-131">Por exemplo, um componente contendo uma instrução SQL em uma propriedade personalizada que controla os dados definidos para o componente pode adicionar suas colunas de saída durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-131">For example, a component that contains a SQL statement in a custom property that controls the data set for the component may add its output columns during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A> method.</span></span> <span data-ttu-id="2e040-132">O componente verifica se possui uma conexão em cache e, em caso afirmativo, conecta-se à fonte de dados e gera suas colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="2e040-132">The component checks to see whether it has a cached connection, and, if it does, connects to the data source and generates its output columns.</span></span>

 <span data-ttu-id="2e040-133">Depois da criação de uma coluna de saída, defina suas propriedades de tipo de dados chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-133">After an output column has been created, set its data type properties by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="2e040-134">Esse método é necessário porque as propriedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> são somente leitura e elas dependem das definições umas das outras.</span><span class="sxs-lookup"><span data-stu-id="2e040-134">This method is necessary because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are read-only and each property is dependent on the settings of the other.</span></span> <span data-ttu-id="2e040-135">Esse método força a definição consistente desses valores, e a tarefa de fluxo de dados valida que eles sejam definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="2e040-135">This method enforces the need for these values to be set consistently, and the data flow task validates that they are set correctly.</span></span>

 <span data-ttu-id="2e040-136">O <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> da coluna determina os valores que são definidos para as outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e040-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="2e040-137">A tabela a seguir mostra os requisitos nas propriedades dependentes para cada <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-137">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="2e040-138">Os tipos de dados não listados têm as propriedades dependentes definidas como zero.</span><span class="sxs-lookup"><span data-stu-id="2e040-138">The data types not listed have their dependent properties set to zero.</span></span>

|<span data-ttu-id="2e040-139">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2e040-139">DataType</span></span>|<span data-ttu-id="2e040-140">Comprimento</span><span class="sxs-lookup"><span data-stu-id="2e040-140">Length</span></span>|<span data-ttu-id="2e040-141">Escala</span><span class="sxs-lookup"><span data-stu-id="2e040-141">Scale</span></span>|<span data-ttu-id="2e040-142">Precisão</span><span class="sxs-lookup"><span data-stu-id="2e040-142">Precision</span></span>|<span data-ttu-id="2e040-143">CodePage</span><span class="sxs-lookup"><span data-stu-id="2e040-143">CodePage</span></span>|
|--------------|------------|-----------|---------------|--------------|
|<span data-ttu-id="2e040-144">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="2e040-144">DT_DECIMAL</span></span>|<span data-ttu-id="2e040-145">0</span><span class="sxs-lookup"><span data-stu-id="2e040-145">0</span></span>|<span data-ttu-id="2e040-146">Maior que 0 e menor ou igual a 28.</span><span class="sxs-lookup"><span data-stu-id="2e040-146">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="2e040-147">0</span><span class="sxs-lookup"><span data-stu-id="2e040-147">0</span></span>|<span data-ttu-id="2e040-148">0</span><span class="sxs-lookup"><span data-stu-id="2e040-148">0</span></span>|
|<span data-ttu-id="2e040-149">DT_CY</span><span class="sxs-lookup"><span data-stu-id="2e040-149">DT_CY</span></span>|<span data-ttu-id="2e040-150">0</span><span class="sxs-lookup"><span data-stu-id="2e040-150">0</span></span>|<span data-ttu-id="2e040-151">0</span><span class="sxs-lookup"><span data-stu-id="2e040-151">0</span></span>|<span data-ttu-id="2e040-152">0</span><span class="sxs-lookup"><span data-stu-id="2e040-152">0</span></span>|<span data-ttu-id="2e040-153">0</span><span class="sxs-lookup"><span data-stu-id="2e040-153">0</span></span>|
|<span data-ttu-id="2e040-154">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="2e040-154">DT_NUMERIC</span></span>|<span data-ttu-id="2e040-155">0</span><span class="sxs-lookup"><span data-stu-id="2e040-155">0</span></span>|<span data-ttu-id="2e040-156">Maior que 0 e menor ou igual a 28, e menor que a Precisão.</span><span class="sxs-lookup"><span data-stu-id="2e040-156">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="2e040-157">Maior ou igual a 1 e menor ou igual a 38.</span><span class="sxs-lookup"><span data-stu-id="2e040-157">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="2e040-158">0</span><span class="sxs-lookup"><span data-stu-id="2e040-158">0</span></span>|
|<span data-ttu-id="2e040-159">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="2e040-159">DT_BYTES</span></span>|<span data-ttu-id="2e040-160">Maior que 0.</span><span class="sxs-lookup"><span data-stu-id="2e040-160">Greater than 0.</span></span>|<span data-ttu-id="2e040-161">0</span><span class="sxs-lookup"><span data-stu-id="2e040-161">0</span></span>|<span data-ttu-id="2e040-162">0</span><span class="sxs-lookup"><span data-stu-id="2e040-162">0</span></span>|<span data-ttu-id="2e040-163">0</span><span class="sxs-lookup"><span data-stu-id="2e040-163">0</span></span>|
|<span data-ttu-id="2e040-164">DT_STR</span><span class="sxs-lookup"><span data-stu-id="2e040-164">DT_STR</span></span>|<span data-ttu-id="2e040-165">Maior que 0 e menor que 8000.</span><span class="sxs-lookup"><span data-stu-id="2e040-165">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="2e040-166">0</span><span class="sxs-lookup"><span data-stu-id="2e040-166">0</span></span>|<span data-ttu-id="2e040-167">0</span><span class="sxs-lookup"><span data-stu-id="2e040-167">0</span></span>|<span data-ttu-id="2e040-168">Não 0 e uma página de código válida.</span><span class="sxs-lookup"><span data-stu-id="2e040-168">Not 0, and a valid code page.</span></span>|
|<span data-ttu-id="2e040-169">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="2e040-169">DT_WSTR</span></span>|<span data-ttu-id="2e040-170">Maior que 0 e menor que 4.000.</span><span class="sxs-lookup"><span data-stu-id="2e040-170">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="2e040-171">0</span><span class="sxs-lookup"><span data-stu-id="2e040-171">0</span></span>|<span data-ttu-id="2e040-172">0</span><span class="sxs-lookup"><span data-stu-id="2e040-172">0</span></span>|<span data-ttu-id="2e040-173">0</span><span class="sxs-lookup"><span data-stu-id="2e040-173">0</span></span>|

 <span data-ttu-id="2e040-174">Como as restrições nas propriedades de tipo de dados são baseadas no tipo de dados da coluna de saída, você deve escolher o tipo de dados correto do [!INCLUDE[ssIS](../../includes/ssis-md.md)] quando trabalha com tipos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="2e040-174">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="2e040-175">A classe base fornece três métodos auxiliares, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, para ajudar desenvolvedores de componentes gerenciados a selecionar um tipo de dados [!INCLUDE[ssIS](../../includes/ssis-md.md)], considerando um tipo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="2e040-175">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, to assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="2e040-176">Esses métodos convertem tipos de dados gerenciados em tipos de dados do [!INCLUDE[ssIS](../../includes/ssis-md.md)] e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="2e040-176">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>

 <span data-ttu-id="2e040-177">O exemplo de código a seguir mostra como a coleção de colunas de saída de um componente é preenchida com base no esquema de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2e040-177">The following code example shows how the output column collection of a component is populated based on the schema of a table.</span></span> <span data-ttu-id="2e040-178">Os métodos auxiliares da classe base são usados para definir o tipo de dados da coluna e as propriedades dependentes são definidas com base no tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="2e040-178">The helper methods of the base class are used to set the data type of the column, and the dependent properties are set based on the data type.</span></span>

```csharp
SqlCommand sqlCommand;

private void CreateColumnsFromDataTable()
{
    // Get the output.
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    // Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll();
    output.ExternalMetadataColumnCollection.RemoveAll();

    this.sqlCommand = sqlConnection.CreateCommand();
    this.sqlCommand.CommandType = CommandType.Text;
    this.sqlCommand.CommandText = (string)ComponentMetaData.CustomPropertyCollection["SqlStatement"].Value;
    SqlDataReader schemaReader = this.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly);
    DataTable dataTable = schemaReader.GetSchemaTable();

    // Walk the columns in the schema, 
    // and for each data column create an output column and an external metadata column.
    foreach (DataRow row in dataTable.Rows)
    {
        IDTSOutputColumn100 outColumn = output.OutputColumnCollection.New();
        IDTSExternalMetadataColumn100 exColumn = output.ExternalMetadataColumnCollection.New();

        // Set column data type properties.
        bool isLong = false;
        DataType dt = DataRecordTypeToBufferType((Type)row["DataType"]);
        dt = ConvertBufferDataTypeToFitManaged(dt, ref isLong);
        int length = 0;
        int precision = (short)row["NumericPrecision"];
        int scale = (short)row["NumericScale"];
        int codepage = dataTable.Locale.TextInfo.ANSICodePage;

        switch (dt)
        {
            // The length cannot be zero, and the code page property must contain a valid code page.
            case DataType.DT_STR:
            case DataType.DT_TEXT:
                length = precision;
                precision = 0;
                scale = 0;
                break;

            case DataType.DT_WSTR:
                length = precision;
                codepage = 0;
                scale = 0;
                precision = 0;
                break;

            case DataType.DT_BYTES:
                precision = 0;
                scale = 0;
                codepage = 0;
                break;

            case DataType.DT_NUMERIC:
                length = 0;
                codepage = 0;

                if (precision > 38)
                    precision = 38;

                if (scale > 6)
                    scale = 6;
                break;

            case DataType.DT_DECIMAL:
                length = 0;
                precision = 0;
                codepage = 0;
                break;

            default:
                length = 0;
                precision = 0;
                codepage = 0;
                scale = 0;
                break;

        }

        // Set the properties of the output column.
        outColumn.Name = (string)row["ColumnName"];
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage);
    }
}
```

```vb
Private sqlCommand As SqlCommand

Private Sub CreateColumnsFromDataTable()

    ' Get the output.
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    ' Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll()
    output.ExternalMetadataColumnCollection.RemoveAll()

    Me.sqlCommand = sqlConnection.CreateCommand()
    Me.sqlCommand.CommandType = CommandType.Text
    Me.sqlCommand.CommandText = CStr(ComponentMetaData.CustomPropertyCollection("SqlStatement").Value)

    Dim schemaReader As SqlDataReader = Me.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly)
    Dim dataTable As DataTable = schemaReader.GetSchemaTable()

    ' Walk the columns in the schema, 
    ' and for each data column create an output column and an external metadata column.
    For Each row As DataRow In dataTable.Rows

        Dim outColumn As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        Dim exColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()

        ' Set column data type properties.
        Dim isLong As Boolean = False
        Dim dt As DataType = DataRecordTypeToBufferType(CType(row("DataType"), Type))
        dt = ConvertBufferDataTypeToFitManaged(dt, isLong)
        Dim length As Integer = 0
        Dim precision As Integer = CType(row("NumericPrecision"), Short)
        Dim scale As Integer = CType(row("NumericScale"), Short)
        Dim codepage As Integer = dataTable.Locale.TextInfo.ANSICodePage

        Select Case dt

            ' The length cannot be zero, and the code page property must contain a valid code page.
            Case DataType.DT_STR
            Case DataType.DT_TEXT
                length = precision
                precision = 0
                scale = 0

            Case DataType.DT_WSTR
                length = precision
                codepage = 0
                scale = 0
                precision = 0

            Case DataType.DT_BYTES
                precision = 0
                scale = 0
                codepage = 0

            Case DataType.DT_NUMERIC
                length = 0
                codepage = 0

                If precision > 38 Then
                    precision = 38
                End If

                If scale > 6 Then
                    scale = 6
                End If

            Case DataType.DT_DECIMAL
                length = 0
                precision = 0
                codepage = 0

            Case Else
                length = 0
                precision = 0
                codepage = 0
                scale = 0
        End Select

        ' Set the properties of the output column.
        outColumn.Name = CStr(row("ColumnName"))
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage)
    Next
End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="2e040-179">Validando o componente</span><span class="sxs-lookup"><span data-stu-id="2e040-179">Validating the Component</span></span>
 <span data-ttu-id="2e040-180">Procure validar um componente de origem e verificar se as colunas definidas nas suas coleções de colunas de saída coincidem com as colunas da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="2e040-180">You should validate a source component and verify that the columns defined in its output column collections match the columns at the external data source.</span></span> <span data-ttu-id="2e040-181">Às vezes, pode ser impossível verificar as colunas de saída em relação à fonte de dados externa, como, por exemplo, em um estado desconectado ou quando é preferível evitar viagens de ida e volta demoradas ao servidor.</span><span class="sxs-lookup"><span data-stu-id="2e040-181">Sometimes, verifying the output columns against the external data source can be impossible, such as in a disconnected state, or when it is preferable to avoid lengthy round trips to the server.</span></span> <span data-ttu-id="2e040-182">Nessas situações, as colunas da saída ainda podem ser validadas através do <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> do objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="2e040-182">In these situations, the columns in the output can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> of the output object.</span></span> <span data-ttu-id="2e040-183">Para obter mais informações, consulte [Validando um componente de fluxo de dados](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2e040-183">For more information, see [Validating a Data Flow Component](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span>

 <span data-ttu-id="2e040-184">Essa coleção existe em objetos de entrada e saída e você pode preenchê-la com as colunas da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="2e040-184">This collection exists on both input and output objects and you can populate it with the columns from the external data source.</span></span> <span data-ttu-id="2e040-185">Você pode usar essa coleção para validar as colunas de saída quando o Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] está offline, quando o componente está desconectado ou quando a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> é `false`.</span><span class="sxs-lookup"><span data-stu-id="2e040-185">You can use this collection to validate the output columns when [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span> <span data-ttu-id="2e040-186">A coleção deve ser preenchida primeiro ao mesmo tempo que as colunas de saída são criadas.</span><span class="sxs-lookup"><span data-stu-id="2e040-186">The collection should be first populated at the same time that the output columns are created.</span></span> <span data-ttu-id="2e040-187">É relativamente fácil adicionar colunas de metadados externas à coleção pois a coluna de metadados externa inicialmente deve corresponder à coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="2e040-187">Adding external metadata columns to the collection is relatively easy because the external metadata column should initially match the output column.</span></span> <span data-ttu-id="2e040-188">As propriedades de tipo de dados da coluna já deveriam ter sido definidas corretamente e as propriedades podem ser copiadas diretamente no objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100>.</span><span class="sxs-lookup"><span data-stu-id="2e040-188">The data type properties of the column should have already been set correctly, and the properties can be copied directly to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100> object.</span></span>

 <span data-ttu-id="2e040-189">O código de exemplo a seguir adiciona uma coluna de metadados externa que se baseia em uma coluna de saída recém-criada.</span><span class="sxs-lookup"><span data-stu-id="2e040-189">The following sample code adds an external metadata column that is based on a newly created output column.</span></span> <span data-ttu-id="2e040-190">Ele pressupõe que a coluna de saída já foi criada.</span><span class="sxs-lookup"><span data-stu-id="2e040-190">It assumes that the output column has already been created.</span></span>

```csharp
private void CreateExternalMetaDataColumn(IDTSOutput100 output, IDTSOutputColumn100 outputColumn)
{

    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = output.ExternalMetadataColumnCollection.New();
    externalColumn.Name = outputColumn.Name;
    externalColumn.Precision = outputColumn.Precision;
    externalColumn.Length = outputColumn.Length;
    externalColumn.DataType = outputColumn.DataType;
    externalColumn.Scale = outputColumn.Scale;

    // Map the external column to the output column.
    outputColumn.ExternalMetadataColumnID = externalColumn.ID;

}
```

```vb
Private Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumn As IDTSOutputColumn100)

        ' Set the properties of the external metadata column.
        Dim externalColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()
        externalColumn.Name = outputColumn.Name
        externalColumn.Precision = outputColumn.Precision
        externalColumn.Length = outputColumn.Length
        externalColumn.DataType = outputColumn.DataType
        externalColumn.Scale = outputColumn.Scale

        ' Map the external column to the output column.
        outputColumn.ExternalMetadataColumnID = externalColumn.ID

    End Sub
```

## <a name="run-time"></a><span data-ttu-id="2e040-191">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="2e040-191">Run Time</span></span>
 <span data-ttu-id="2e040-192">Durante a execução, componentes adicionam linhas para gerar buffers que são criados pela tarefa de fluxo de dados e são fornecidos ao componente em <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-192">During execution, components add rows to output buffers that are created by the data flow task and provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="2e040-193">Chamado uma vez para componentes de origem, o método recebe um buffer de saída para cada <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> do componente que é conectado a um componente downstream.</span><span class="sxs-lookup"><span data-stu-id="2e040-193">Called once for source components, the method receives an output buffer for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the component that is connected to a downstream component.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="2e040-194">Localizando colunas no buffer</span><span class="sxs-lookup"><span data-stu-id="2e040-194">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="2e040-195">O buffer de saída para um componente contém as colunas definidas pelo componente e quaisquer colunas adicionadas à saída de um componente downstream.</span><span class="sxs-lookup"><span data-stu-id="2e040-195">The output buffer for a component contains the columns defined by the component and any columns added to the output of a downstream component.</span></span> <span data-ttu-id="2e040-196">Por exemplo, se um componente de origem fornecer três colunas na saída e o próximo componente adicionar uma quarta coluna de saída, o buffer de saída fornecido para uso pelo componente de origem conterá essas quatro colunas.</span><span class="sxs-lookup"><span data-stu-id="2e040-196">For example, if a source component provides three columns in its output, and the next component adds a fourth output column, the output buffer provided for use by the source component contains these four columns.</span></span>

 <span data-ttu-id="2e040-197">A ordem das colunas em uma linha de buffer não é definida pelo índice da coluna de saída na coleção de colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="2e040-197">The order of the columns in a buffer row is not defined by the index of the output column in the output column collection.</span></span> <span data-ttu-id="2e040-198">Uma coluna de saída só pode ser localizada com precisão em uma linha de buffer através do método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-198">An output column can only be accurately located in a buffer row by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="2e040-199">Esse método localiza a coluna com a ID de linhagem especificada no buffer especificado e retorna sua localização na linha.</span><span class="sxs-lookup"><span data-stu-id="2e040-199">This method locates the column with the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="2e040-200">Os índices das colunas de saída costumam estar localizados no método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> e são armazenados para uso durante o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-200">The indexes of the output columns are typically located in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and stored for use during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span>

 <span data-ttu-id="2e040-201">O exemplo de código a seguir indica a localização das colunas de saída no buffer de saída durante uma chamada ao <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> e armazena-as em uma estrutura interna.</span><span class="sxs-lookup"><span data-stu-id="2e040-201">The following code example finds the location of the output columns in the output buffer during a call to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, and stores them in an internal structure.</span></span> <span data-ttu-id="2e040-202">O nome da coluna também é armazenado na estrutura e é usado no exemplo de código para o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> na próxima seção desse tópico.</span><span class="sxs-lookup"><span data-stu-id="2e040-202">The name of the column is also stored in the structure and is used in the code example for the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method in the next section of this topic.</span></span>

```csharp
ArrayList columnInformation;

private struct ColumnInfo
{
    public int BufferColumnIndex;
    public string ColumnName;
}

public override void PreExecute()
{
    this.columnInformation = new ArrayList();
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    foreach (IDTSOutputColumn100 col in output.OutputColumnCollection)
    {
        ColumnInfo ci = new ColumnInfo();
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID);
        ci.ColumnName = col.Name;
        columnInformation.Add(ci);
    }
}
```

```vb
Public Overrides Sub PreExecute()

    Me.columnInformation = New ArrayList()
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    For Each col As IDTSOutputColumn100 In output.OutputColumnCollection

        Dim ci As ColumnInfo = New ColumnInfo()
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID)
        ci.ColumnName = col.Name
        columnInformation.Add(ci)
    Next
End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="2e040-203">Processando linhas</span><span class="sxs-lookup"><span data-stu-id="2e040-203">Processing Rows</span></span>
 <span data-ttu-id="2e040-204">São adicionadas linhas ao buffer de saída chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> que cria uma nova linha de buffer com valores vazios em suas colunas.</span><span class="sxs-lookup"><span data-stu-id="2e040-204">Rows are added to the output buffer by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method, which creates a new buffer row with empty values in its columns.</span></span> <span data-ttu-id="2e040-205">O componente atribui valores a cada coluna.</span><span class="sxs-lookup"><span data-stu-id="2e040-205">The component then assigns values to the individual columns.</span></span> <span data-ttu-id="2e040-206">Os buffers de saída fornecidos a um componente são criados e monitorados pela tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="2e040-206">The output buffers provided to a component are created and monitored by the data flow task.</span></span> <span data-ttu-id="2e040-207">Quando ficam cheias, a linhas do buffer são transferidas para o próximo componente.</span><span class="sxs-lookup"><span data-stu-id="2e040-207">As they become full, the rows in the buffer are moved to the next component.</span></span> <span data-ttu-id="2e040-208">Não é possível determinar quando um lote de linhas é enviado ao próximo componente pois a movimentação de linhas pela tarefa de fluxo de dados é transparente para o desenvolvedor de componentes, e a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> é sempre zero nos buffers de saída.</span><span class="sxs-lookup"><span data-stu-id="2e040-208">There is no way to determine when a batch of rows has been sent to the next component because the movement of rows by the data flow task is transparent to the component developer, and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> property is always zero on output buffers.</span></span> <span data-ttu-id="2e040-209">Quando um componente de origem termina de adicionar linhas ao seu buffer de saída, ele notifica a tarefa de fluxo de dados, chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, e as demais linhas do buffer são transmitidas ao próximo componente.</span><span class="sxs-lookup"><span data-stu-id="2e040-209">When a source component is finished adding rows to its output buffer, it notifies the data flow task by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, and the remaining rows in the buffer are passed to the next component.</span></span>

 <span data-ttu-id="2e040-210">Apesar de o componente de origem ler linhas da fonte de dados externa, talvez você queira atualizar o contador de desempenho "Linhas lidas" ou "Bytes de BLOB lidos", chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-210">While the source component reads rows from the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="2e040-211">Para obter mais informações, consulte [Performance Counters](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="2e040-211">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="2e040-212">O exemplo de código a seguir mostra um componente que adiciona linhas a um buffer de saída em <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e040-212">The following code example shows a component that adds rows to an output buffer in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="2e040-213">Os índices das colunas de saída no buffer foram localizados através do <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> no exemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="2e040-213">The indexes of the output columns in the buffer were located using <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the previous code example.</span></span>

```csharp
public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
{
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
    PipelineBuffer buffer = buffers[0];

    SqlDataReader dataReader = sqlCommand.ExecuteReader();

    // Loop over the rows in the DataReader, 
    // and add them to the output buffer.
    while (dataReader.Read())
    {
        // Add a row to the output buffer.
        buffer.AddRow();

        for (int x = 0; x < columnInformation.Count; x++)
        {
            ColumnInfo ci = (ColumnInfo)columnInformation[x];
            int ordinal = dataReader.GetOrdinal(ci.ColumnName);

            if (dataReader.IsDBNull(ordinal))
                buffer.SetNull(ci.BufferColumnIndex);
            else
            {
                buffer[ci.BufferColumnIndex] = dataReader[ci.ColumnName];
            }
        }
    }
    buffer.SetEndOfRowset();
}
```

```vb
Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim buffer As PipelineBuffer = buffers(0)

    Dim dataReader As SqlDataReader = sqlCommand.ExecuteReader()

    ' Loop over the rows in the DataReader, 
    ' and add them to the output buffer.
    While (dataReader.Read())

        ' Add a row to the output buffer.
        buffer.AddRow()

        For x As Integer = 0 To columnInformation.Count

            Dim ci As ColumnInfo = CType(columnInformation(x), ColumnInfo)

            Dim ordinal As Integer = dataReader.GetOrdinal(ci.ColumnName)

            If (dataReader.IsDBNull(ordinal)) Then
                buffer.SetNull(ci.BufferColumnIndex)
            Else
                buffer(ci.BufferColumnIndex) = dataReader(ci.ColumnName)

            End If
        Next

    End While

    buffer.SetEndOfRowset()
End Sub
```

## <a name="sample"></a><span data-ttu-id="2e040-214">Amostra</span><span class="sxs-lookup"><span data-stu-id="2e040-214">Sample</span></span>
 <span data-ttu-id="2e040-215">O exemplo a seguir mostra um componente de origem simples que usa um gerenciador de conexões do Arquivo para carregar o conteúdo binário dos arquivos no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="2e040-215">The following sample shows a simple source component that uses a File connection manager to load the binary contents of files into the data flow.</span></span> <span data-ttu-id="2e040-216">Esse exemplo não demonstra todos os métodos e todas as funcionalidades discutidas nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="2e040-216">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="2e040-217">Ele demonstra os métodos importantes que todo componente de origem personalizado deve substituir, mas não contém código para a validação em tempo de design.</span><span class="sxs-lookup"><span data-stu-id="2e040-217">It demonstrates the important methods that every custom source component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace BlobSrc
{
  [DtsPipelineComponent(DisplayName = "BLOB Inserter Source", Description = "Inserts files into the data flow as BLOBs")]
  public class BlobSrc : PipelineComponent
  {
    IDTSConnectionManager100 m_ConnMgr;
    int m_FileNameColumnIndex = -1;
    int m_FileBlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
      output.Name = "BLOB File Inserter Output";

      IDTSOutputColumn100 column = output.OutputColumnCollection.New();
      column.Name = "FileName";
      column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0);

      column = output.OutputColumnCollection.New();
      column.Name = "FileBLOB";
      column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0);

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_ConnMgr = conn.ConnectionManager;
    }

    public override void ReleaseConnections()
    {
      m_ConnMgr = null;
    }

    public override void PreExecute()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

      m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[0].LineageID);
      m_FileBlobColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[1].LineageID);
    }

    public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
    {
      string strFileName = (string)m_ConnMgr.AcquireConnection(null);

      while (strFileName != null)
      {
        buffers[0].AddRow();

        buffers[0].SetString(m_FileNameColumnIndex, strFileName);

        FileInfo fileInfo = new FileInfo(strFileName);
        byte[] fileData = new byte[fileInfo.Length];
        FileStream fs = new FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read);
        fs.Read(fileData, 0, fileData.Length);

        buffers[0].AddBlobData(m_FileBlobColumnIndex, fileData);

        strFileName = (string)m_ConnMgr.AcquireConnection(null);
      }

      buffers[0].SetEndOfRowset();
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper 
Namespace BlobSrc 

 <DtsPipelineComponent(DisplayName="BLOB Inserter Source", Description="Inserts files into the data flow as BLOBs")> _ 
 Public Class BlobSrc 
 Inherits PipelineComponent 
   Private m_ConnMgr As IDTSConnectionManager100 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_FileBlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New 
     output.Name = "BLOB File Inserter Output" 
     Dim column As IDTSOutputColumn100 = output.OutputColumnCollection.New 
     column.Name = "FileName" 
     column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0) 
     column = output.OutputColumnCollection.New 
     column.Name = "FileBLOB" 
     column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0) 
     Dim conn As IDTSRuntimeConnection90 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_ConnMgr = conn.ConnectionManager 
   End Sub 

   Public  Overrides Sub ReleaseConnections() 
     m_ConnMgr = Nothing 
   End Sub 

   Public  Overrides Sub PreExecute() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0) 
     m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(0).LineageID), Integer) 
     m_FileBlobColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(1).LineageID), Integer) 
   End Sub 

   Public  Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer()) 
     Dim strFileName As String = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     While Not (strFileName Is Nothing) 
       buffers(0).AddRow 
       buffers(0).SetString(m_FileNameColumnIndex, strFileName) 
       Dim fileInfo As FileInfo = New FileInfo(strFileName) 
       Dim fileData(fileInfo.Length) As Byte 
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read) 
       fs.Read(fileData, 0, fileData.Length) 
       buffers(0).AddBlobData(m_FileBlobColumnIndex, fileData) 
       strFileName = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     End While 
     buffers(0).SetEndOfRowset 
   End Sub 
 End Class 
End Namespace
```

<span data-ttu-id="2e040-218">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2e040-218">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2e040-219">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="2e040-219">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2e040-220">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="2e040-220">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2e040-221">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="2e040-221">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e040-222">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e040-222">See Also</span></span>
 <span data-ttu-id="2e040-223">[Desenvolvendo um componente de destino personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [criando uma fonte com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="2e040-223">[Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span></span>


