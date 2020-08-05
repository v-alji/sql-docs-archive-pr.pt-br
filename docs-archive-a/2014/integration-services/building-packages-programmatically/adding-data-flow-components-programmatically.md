---
title: Adicionar componentes de fluxo de dados programaticamente | Microsoft Docs
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
- data flow task [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: c06065cf-43e5-4b6b-9824-7309d7f5e35e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 807e758e42b738c4b0bf64b1d6f48bc29649ae6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572655"
---
# <a name="adding-data-flow-components-programmatically"></a><span data-ttu-id="885c1-102">Adicionando componentes de fluxo de dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="885c1-102">Adding Data Flow Components Programmatically</span></span>
  <span data-ttu-id="885c1-103">Ao compilar um fluxo de dados, comece adicionando componentes.</span><span class="sxs-lookup"><span data-stu-id="885c1-103">When you build a data flow, you start by adding components.</span></span> <span data-ttu-id="885c1-104">Em seguida, configure esses componentes e os conecte para estabelecer o fluxo de dados em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="885c1-104">Then you configure those components and connect them together to establish the flow of data at run time.</span></span> <span data-ttu-id="885c1-105">Esta seção descreve como adicionar um componente à tarefa de fluxo de dados, criar a instância tempo de design do componente e configurar o componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-105">This section describes adding a component to the data flow task, creating the design-time instance of the component, and then configuring the component.</span></span> <span data-ttu-id="885c1-106">Para obter informaçõessobre como conectar componentes, consulte [Conectar componentes do fluxo de dados programaticamente](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="885c1-106">For information about how to connect components, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-component"></a><span data-ttu-id="885c1-107">Adicionando um componente</span><span class="sxs-lookup"><span data-stu-id="885c1-107">Adding a Component</span></span>  
 <span data-ttu-id="885c1-108">Chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> da coleção <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A> para criar um componente novo e adicioná-lo à tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="885c1-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A> collection to create a new component and add it to the data flow task.</span></span> <span data-ttu-id="885c1-109">Este método retorna a interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> do componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-109">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component.</span></span> <span data-ttu-id="885c1-110">Contudo, neste momento, o <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> não contém informações específicas de nenhum componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-110">However, at this point, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> does not contain information specific to any one component.</span></span> <span data-ttu-id="885c1-111">Defina a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> para identificar o tipo de componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-111">Set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property to identify the type of component.</span></span> <span data-ttu-id="885c1-112">A tarefa de fluxo de dados usa o valor dessa propriedade para criar uma instância do componente em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="885c1-112">The data flow task uses the value of this property to create an instance of the component at run time.</span></span>  
  
 <span data-ttu-id="885c1-113">O valor especificado na propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> pode ser o CLSID, o PROGID ou a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> do componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-113">The value specified in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property can be the CLSID, PROGID, or <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property of the component.</span></span> <span data-ttu-id="885c1-114">O CLSID é exibido normalmente na janela Propriedades como o valor da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> do componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-114">The CLSID is normally displayed in the Properties window as the value of the component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="885c1-115">Para obter informações sobre como obter essa propriedade e outras propriedades de componentes disponíveis, consulte [Descobrir componentes de fluxo de dados programaticamente](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="885c1-115">For information about obtaining this property and other properties of available components, see [Discovering Data Flow Components Programmatically](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-managed-component"></a><span data-ttu-id="885c1-116">Adicionando um componente gerenciado</span><span class="sxs-lookup"><span data-stu-id="885c1-116">Adding a Managed Component</span></span>  
 <span data-ttu-id="885c1-117">Não é possível usar o CLSID ou o PROGID para adicionar um dos componentes de fluxo de dados gerenciados ao fluxo de dados, pois esses valores apontam para um wrapper e não para o componente em si.</span><span class="sxs-lookup"><span data-stu-id="885c1-117">You cannot use the CLSID or PROGID to add one the managed data flow components to the data flow, because these values point to a wrapper and not to the component itself.</span></span> <span data-ttu-id="885c1-118">Em vez disso, você pode usar a propriedade `CreationName` ou a propriedade `AssemblyQualifiedName` como mostra o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="885c1-118">Instead you can use the `CreationName` property or the `AssemblyQualifiedName` property as shown in the following sample.</span></span>  
  
 <span data-ttu-id="885c1-119">Se você pretende usar a propriedade `AssemblyQualifiedName`, você deve adicionar uma referência em seu projeto [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ao assembly que contém o componente gerenciado.</span><span class="sxs-lookup"><span data-stu-id="885c1-119">If you intend to use the `AssemblyQualifiedName` property, then you must add a reference in your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] project to the assembly that contains the managed component.</span></span> <span data-ttu-id="885c1-120">Esses assemblies não são listados na guia .NET da caixa de diálogo **Adicionar Referência**.</span><span class="sxs-lookup"><span data-stu-id="885c1-120">These assemblies are not listed on the .NET tab of the **Add Reference** dialog box.</span></span> <span data-ttu-id="885c1-121">Normalmente, você deve navegar para localizar o assembly na pasta **C:\Program Files\Microsoft SQL Server\100\DTS\PipelineComponents**.</span><span class="sxs-lookup"><span data-stu-id="885c1-121">Normally you must browse to locate the assembly in the **C:\Program Files\Microsoft SQL Server\100\DTS\PipelineComponents** folder.</span></span>  
  
 <span data-ttu-id="885c1-122">Os componentes de fluxo de dados gerenciados embutidos incluem:</span><span class="sxs-lookup"><span data-stu-id="885c1-122">The built-in managed data flow components include:</span></span>  
  
-   [!INCLUDE[vstecado](../../includes/vstecado-md.md)] <span data-ttu-id="885c1-123">Origem</span><span class="sxs-lookup"><span data-stu-id="885c1-123">Source</span></span>  
  
-   <span data-ttu-id="885c1-124">Origem XML</span><span class="sxs-lookup"><span data-stu-id="885c1-124">XML Source</span></span>  
  
-   <span data-ttu-id="885c1-125">Destino DataReader</span><span class="sxs-lookup"><span data-stu-id="885c1-125">DataReader Destination</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="885c1-126">Destino Compact</span><span class="sxs-lookup"><span data-stu-id="885c1-126">Compact Destination</span></span>  
  
-   <span data-ttu-id="885c1-127">Componente Script</span><span class="sxs-lookup"><span data-stu-id="885c1-127">Script Component</span></span>  
  
 <span data-ttu-id="885c1-128">O exemplo de código seguinte mostra ambos os modos de adicionar um componente gerenciado ao fluxo de dados:</span><span class="sxs-lookup"><span data-stu-id="885c1-128">The following code sample shows both ways of adding a managed component to the data flow:</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Microsoft.SqlServer.Dts.Runtime.Package package = new Microsoft.SqlServer.Dts.Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Microsoft.SqlServer.Dts.Runtime.TaskHost thMainPipe = (Microsoft.SqlServer.Dts.Runtime.TaskHost)e;  
      MainPipe dataFlowTask = (MainPipe)thMainPipe.InnerObject;  
  
      // The Application object will be used to obtain the CreationName  
      //  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
      Application app = new Application();  
  
      // Add a first ADO NET source to the data flow.  
      //  The CreationName property requires an Application instance.  
      IDTSComponentMetaData100 component1 = dataFlowTask.ComponentMetaDataCollection.New();  
      component1.Name = "DataReader Source";  
      component1.ComponentClassID = app.PipelineComponentInfos["DataReader Source"].CreationName;  
  
      // Add a second ADO NET source to the data flow.  
      //  The AssemblyQualifiedName property requires a reference to the assembly.  
      IDTSComponentMetaData100 component2 = dataFlowTask.ComponentMetaDataCollection.New();  
      component2.Name = "DataReader Source";  
      component2.ComponentClassID = typeof(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName;  
    }  
  }  
}  
  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' The Application object will be used to obtain the CreationName  
    '  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
    Dim app As New Application()  
  
    ' Add a first ADO NET source to the data flow.  
    '  The CreationName property requires an Application instance.  
    Dim component1 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component1.Name = "DataReader Source"  
    component1.ComponentClassID = app.PipelineComponentInfos("DataReader Source").CreationName  
  
    ' Add a second ADO NET source to the data flow.  
    '  The AssemblyQualifiedName property requires a reference to the assembly.  
    Dim component2 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component2.Name = "DataReader Source"  
    component2.ComponentClassID = _  
      GetType(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName  
  
  End Sub  
  
End Module  
```  
  
## <a name="creating-the-design-time-instance-of-the-component"></a><span data-ttu-id="885c1-129">Criando a instância tempo de design do componente</span><span class="sxs-lookup"><span data-stu-id="885c1-129">Creating the Design-time Instance of the Component</span></span>  
 <span data-ttu-id="885c1-130">Chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> para criar a instância tempo de design do componente identificada pela propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>.</span><span class="sxs-lookup"><span data-stu-id="885c1-130">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method to create the design time instance of the component identified by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="885c1-131">Esse método retorna o objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper>, que é o wrapper gerenciado para a interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="885c1-131">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> object, which is the managed wrapper for the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="885c1-132">Sempre que possível, você deve modificar um componente usando os métodos da instância tempo de design em vez de modificar os metadados do componente diretamente.</span><span class="sxs-lookup"><span data-stu-id="885c1-132">Whenever possible, you should modify a component by using the methods of the design-time instance instead of by modifying the component metadata directly.</span></span> <span data-ttu-id="885c1-133">Embora existam itens nos metadados que você deve definir diretamente, como as conexões, em geral não se aconselha modificar os metadados diretamente, pois assim você ignora a capacidade do componente de monitorar e validar alterações.</span><span class="sxs-lookup"><span data-stu-id="885c1-133">Although there are items in the metadata that you must set directly, such as connections, generally it is inadvisable to modify the metadata directly because you bypass the ability of the component to monitor and validate changes.</span></span>  
  
## <a name="assigning-connections"></a><span data-ttu-id="885c1-134">Atribuindo conexões</span><span class="sxs-lookup"><span data-stu-id="885c1-134">Assigning Connections</span></span>  
 <span data-ttu-id="885c1-135">Alguns componentes, como o componente Origem OLE DB, requerem uma conexão com dados externos e usam um objeto <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> existente no pacote para esse propósito.</span><span class="sxs-lookup"><span data-stu-id="885c1-135">Some components, such as the OLE DB Source component, require a connection to external data and use an existing <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object in the package for this purpose.</span></span> <span data-ttu-id="885c1-136">A propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> da coleção <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> indica o número de objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> em tempo de execução requeridos pelo componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection indicates the number of run-time <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects required by the component.</span></span> <span data-ttu-id="885c1-137">Se a contagem for maior que zero, o componente precisará de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="885c1-137">If the count is greater than zero, the component requires a connection.</span></span> <span data-ttu-id="885c1-138">Atribua um gerenciador de conexões do pacote para o componente especificando as propriedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> da primeira conexão no <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="885c1-138">Assign a connection manager from the package to the component by specifying the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> properties of the first connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span> <span data-ttu-id="885c1-139">Observe que o nome do gerenciador de conexões na coleção de conexões em tempo de execução deve corresponder ao nome do gerenciador de conexões referenciado do pacote.</span><span class="sxs-lookup"><span data-stu-id="885c1-139">Note that the name of the connection manager in the run-time connection collection must match the name of the connection managerreferenced from the package.</span></span>  
  
## <a name="setting-the-values-of-custom-properties"></a><span data-ttu-id="885c1-140">Definindo os valores de propriedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="885c1-140">Setting the Values of Custom Properties</span></span>  
 <span data-ttu-id="885c1-141">Depois de criar a instância tempo de design do componente, chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="885c1-141">After creating the design-time instance of the component, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="885c1-142">Esse método é similar a um construtor por que ele inicializa um componente recém-criado criando suas propriedades personalizadas e seus objetos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="885c1-142">This method is similar to a constructor because it initializes a newly created component by creating its custom properties and its input and output objects.</span></span> <span data-ttu-id="885c1-143">Não chame <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> mais de uma vez em um componente, pois o componente pode se redefinir e perder qualquer modificação feita em seus metadados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="885c1-143">Do not call <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> more than one time on a component, because the component may reset itself and lose any modifications previously made to its metadata.</span></span>  
  
 <span data-ttu-id="885c1-144">O <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> do componente contém uma coleção de objetos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> específicos ao componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-144">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> of the component contains a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> objects specific to the component.</span></span> <span data-ttu-id="885c1-145">Ao contrário de outros modelos de programação, em que as propriedades de um objeto são sempre visíveis no objeto, os componentes preenchem somente suas coleções de propriedades personalizadas quando você chama o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="885c1-145">Unlike other programming models, where the properties of an object are always visible on the object, components only populate their custom property collections when you call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="885c1-146">Depois de chamar o método, use o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> da instância tempo de design do componente para atribuir valores a suas propriedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="885c1-146">After you call method, use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> method of the design-time instance of the component to assign values to its custom properties.</span></span> <span data-ttu-id="885c1-147">Esse método aceita um par nome/valor que identifica a propriedade personalizada e fornece seu valor novo.</span><span class="sxs-lookup"><span data-stu-id="885c1-147">This method accepts a name/value pair that identifies the custom property and provides its new value.</span></span>  
  
## <a name="initializing-output-columns"></a><span data-ttu-id="885c1-148">Inicializando colunas de saída</span><span class="sxs-lookup"><span data-stu-id="885c1-148">Initializing Output Columns</span></span>  
 <span data-ttu-id="885c1-149">Depois de adicionar um componente à tarefa e configurá-lo, inicialize a coleção de colunas no <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> do objeto.</span><span class="sxs-lookup"><span data-stu-id="885c1-149">After you add a component to the task and configure it, initialize the collection of columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the object.</span></span> <span data-ttu-id="885c1-150">Essa etapa é especialmente relevante para componentes de origem, mas não pode inicializar as colunas para componentes de transformação e destino, pois geralmente eles dependem das colunas que recebem dos componentes upstream.</span><span class="sxs-lookup"><span data-stu-id="885c1-150">This step is especially relevant for source components, but may not initialize the columns for transformation and destination components because they generally depend on the columns that they receive from upstream components.</span></span>  
  
 <span data-ttu-id="885c1-151">Chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> para inicializar as colunas nas saídas de um componente de origem.</span><span class="sxs-lookup"><span data-stu-id="885c1-151">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> method to initialize the columns in the outputs of a source component.</span></span> <span data-ttu-id="885c1-152">Como os componentes não se conectam automaticamente a fontes de dados externas, chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> antes de chamar <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> para fornecer ao componente acesso a sua fonte de dados externa e a capacidade de preencher os metadados da sua coluna.</span><span class="sxs-lookup"><span data-stu-id="885c1-152">Because components do not automatically connect to external data sources, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> method before calling <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> to provide the component access to its external data source and the ability to populate its column metadata.</span></span> <span data-ttu-id="885c1-153">Finalmente, chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A> para liberar a conexão.</span><span class="sxs-lookup"><span data-stu-id="885c1-153">Finally, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A> method to release the connection.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="885c1-154">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="885c1-154">Next Step</span></span>  
 <span data-ttu-id="885c1-155">Depois de adicionar e configurar o componente, a próxima etapa é criar caminhos entre componentes, que é discutido no tópico [Criando um caminho entre dois componentes](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="885c1-155">After adding and configuring the component, the next step is to create paths between components, which is discussed in the topic, [Creating a Path Between Two Components](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="885c1-156">Amostra</span><span class="sxs-lookup"><span data-stu-id="885c1-156">Sample</span></span>  
 <span data-ttu-id="885c1-157">O exemplo de código a seguir adiciona o componente Origem OLE DB a uma tarefa de fluxo de dados, cria uma instância tempo de design do componente e configura as propriedades do componente.</span><span class="sxs-lookup"><span data-stu-id="885c1-157">The following code sample adds the OLE DB Source component to a data flow task, creates a design-time instance of the component, and configures the component's properties.</span></span> <span data-ttu-id="885c1-158">Esse exemplo requer uma referência adicional ao assembly Microsoft.SqlServer.DTSRuntimeWrap.</span><span class="sxs-lookup"><span data-stu-id="885c1-158">This example requires an additional reference to the assembly Microsoft.SqlServer.DTSRuntimeWrap.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Runtime.Package package = new Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Runtime.TaskHost thMainPipe = e as Runtime.TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Add an OLEDB connection manager to the package.  
      ConnectionManager cm = package.Connections.Add("OLEDB");  
      cm.Name = "OLEDB ConnectionManager";  
      cm.ConnectionString = "Data Source=(local);" +   
        "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" +   
        "Integrated Security=SSPI;"  
  
      // Add an OLE DB source to the data flow.  
      IDTSComponentMetaData100 component =   
        dataFlowTask.ComponentMetaDataCollection.New();  
      component.Name = "OLEDBSource";  
      component.ComponentClassID = "DTSAdapter.OleDbSource.1";  
      // You can also use the CLSID of the component instead of the PROGID.  
      //component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
      // Get the design time instance of the component.  
      CManagedComponentWrapper instance = component.Instantiate();  
  
      // Initialize the component  
      instance.ProvideComponentProperties();  
  
      // Specify the connection manager.  
      if (component.RuntimeConnectionCollection.Count > 0)  
      {  
        component.RuntimeConnectionCollection[0].ConnectionManager =   
          DtsConvert.GetExtendedInterface(package.Connections[0]);  
        component.RuntimeConnectionCollection[0].ConnectionManagerID =   
          package.Connections[0].ID;      }  
  
      // Set the custom properties.  
      instance.SetComponentProperty("AccessMode", 2);  
      instance.SetComponentProperty("SqlCommand",   
        "Select * from Production.Product");  
  
      // Reinitialize the metadata.  
      instance.AcquireConnections(null);  
      instance.ReinitializeMetaData();  
      instance.ReleaseConnections();  
  
      // Add other components to the data flow and connect them.  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Add an OLEDB connection manager to the package.  
    Dim cm As ConnectionManager = package.Connections.Add("OLEDB")  
    cm.Name = "OLEDB ConnectionManager"  
    cm.ConnectionString = "Data Source=(local);" & _  
      "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;"  
  
    ' Add an OLE DB source to the data flow.  
    Dim component As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component.Name = "OLEDBSource"  
    component.ComponentClassID = "DTSAdapter.OleDbSource.1"  
    ' You can also use the CLSID of the component instead of the PROGID.  
    'component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
    ' Get the design time instance of the component.  
    Dim instance As CManagedComponentWrapper = component.Instantiate()  
  
    ' Initialize the component.  
    instance.ProvideComponentProperties()  
  
    ' Specify the connection manager.  
    If component.RuntimeConnectionCollection.Count > 0 Then  
      component.RuntimeConnectionCollection(0).ConnectionManager = _  
        DtsConvert.GetExtendedInterface(package.Connections(0))  
      component.RuntimeConnectionCollection(0).ConnectionManagerID = _  
        package.Connections(0).ID  
    End If  
  
    ' Set the custom properties.  
    instance.SetComponentProperty("AccessMode", 2)  
    instance.SetComponentProperty("SqlCommand", _  
      "Select * from Production.Product")  
  
    ' Reinitialize the metadata.  
    instance.AcquireConnections(vbNull)  
    instance.ReinitializeMetaData()  
    instance.ReleaseConnections()  
  
    ' Add other components to the data flow and connect them.  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="885c1-159">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="885c1-159">External Resources</span></span>  
 <span data-ttu-id="885c1-160">Entrada no blog, [EzAPI – Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) (EzAPI – atualizado para o SQL Server 2012) em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="885c1-160">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="885c1-161">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="885c1-161">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="885c1-162">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="885c1-162">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="885c1-163">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="885c1-163">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="885c1-164">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="885c1-164">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885c1-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="885c1-165">See Also</span></span>  
 [<span data-ttu-id="885c1-166">Conectando componentes de fluxo de dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="885c1-166">Connecting Data Flow Components Programmatically</span></span>](../building-packages-programmatically/connecting-data-flow-components-programmatically.md)  
  
  
