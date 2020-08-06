---
title: Métodos de tempo de design de um componente de fluxo de dados | Microsoft Docs
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
- custom data flow components [Integration Services], method execution sequence
- ProcessInput method
- method execution sequence [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], method execution sequence
ms.assetid: b5a121a1-b87c-441b-a42c-2cec628dc81c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e33fc4eb5805318dac217d2c5cbaedfd4bca70fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575966"
---
# <a name="design-time-methods-of-a-data-flow-component"></a><span data-ttu-id="728dd-102">Métodos de tempo de design de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="728dd-102">Design-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="728dd-103">Antes da execução, diz-se que a tarefa de fluxo de dados está em um estado de tempo de design, quando sofre alterações incrementais.</span><span class="sxs-lookup"><span data-stu-id="728dd-103">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="728dd-104">As alterações podem incluir a adição ou remoção de componentes, a adição ou remoção dos objetos do caminho que conectam componentes e as alterações nos metadados dos componentes.</span><span class="sxs-lookup"><span data-stu-id="728dd-104">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="728dd-105">Quando ocorrem alterações em metadados, o componente pode monitorar e reagir às alterações.</span><span class="sxs-lookup"><span data-stu-id="728dd-105">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="728dd-106">Por exemplo, um componente pode desabilitar certas alterações ou fazer alterações adicionais em resposta a uma alteração.</span><span class="sxs-lookup"><span data-stu-id="728dd-106">For example, a component can disallow certain changes or make additional changes in response to a change.</span></span> <span data-ttu-id="728dd-107">Em tempo de design, o designer interage com um componente através da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> em tempo de design.</span><span class="sxs-lookup"><span data-stu-id="728dd-107">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>

## <a name="design-time-implementation"></a><span data-ttu-id="728dd-108">Implementação de tempo de design</span><span class="sxs-lookup"><span data-stu-id="728dd-108">Design-Time Implementation</span></span>
 <span data-ttu-id="728dd-109">A interface tempo de design de um componente é descrita pela interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="728dd-109">The design-time interface of a component is described by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span> <span data-ttu-id="728dd-110">Embora você não implemente essa interface explicitamente, uma familiaridade com os métodos definidos nessa interface ajuda você a entender quais métodos da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> correspondem à instância de tempo de design de um componente.</span><span class="sxs-lookup"><span data-stu-id="728dd-110">Although you do not explicitly implement this interface, a familiarity with the methods defined in this interface will help you understand which methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class correspond to the design-time instance of a component.</span></span>

 <span data-ttu-id="728dd-111">Quando um componente é carregado no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], a instância de tempo de design do componente é instanciada e os métodos da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> são chamados à medida que o componente é editado.</span><span class="sxs-lookup"><span data-stu-id="728dd-111">When a component is loaded in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], the design-time instance of the component is instantiated and the methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface are called as the component is edited.</span></span> <span data-ttu-id="728dd-112">A implementação da classe base o deixa anular somente os métodos que seu componente requer.</span><span class="sxs-lookup"><span data-stu-id="728dd-112">The implementation of the base class lets you override only those methods that your component requires.</span></span> <span data-ttu-id="728dd-113">Em muitos casos, você pode anular esses métodos para impedir edições inadequadas a um componente.</span><span class="sxs-lookup"><span data-stu-id="728dd-113">In many cases, you may override these methods to prevent inappropriate edits to a component.</span></span> <span data-ttu-id="728dd-114">Por exemplo, para impedir os usuários de acrescentarem uma saída a um componente, anule o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="728dd-114">For example, to prevent users from adding an output to a component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A> method.</span></span> <span data-ttu-id="728dd-115">Caso contrário, quando a implementação desse método pela classe base for chamada, ela acrescentará uma saída ao componente.</span><span class="sxs-lookup"><span data-stu-id="728dd-115">Otherwise, when the implementation of this method by the base class is called, it adds an output to the component.</span></span>

 <span data-ttu-id="728dd-116">Independentemente do propósito ou funcionalidade de seu componente, você deve anular os métodos <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="728dd-116">Regardless of the purpose or functionality of your component, you should override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> methods.</span></span> <span data-ttu-id="728dd-117">Para obter mais informações sobre <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, consulte [Validar um componente de fluxo de dados](validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="728dd-117">For more information about <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, see [Validating a Data Flow Component](validating-a-data-flow-component.md).</span></span>

## <a name="providecomponentproperties-method"></a><span data-ttu-id="728dd-118">Método ProvideComponentProperties</span><span class="sxs-lookup"><span data-stu-id="728dd-118">ProvideComponentProperties Method</span></span>
 <span data-ttu-id="728dd-119">A inicialização de um componente ocorre no método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="728dd-119">The initialization of a component occurs in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="728dd-120">Esse método é chamado pelo [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer quando um componente é acrescentado à tarefa de fluxo de dados, e é semelhante a um construtor de classe.</span><span class="sxs-lookup"><span data-stu-id="728dd-120">This method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer when a component is added to the data flow task, and is similar to a class constructor.</span></span> <span data-ttu-id="728dd-121">Desenvolvedores de componente devem criar e inicializar suas entradas, saídas e propriedades personalizadas durante essa chamada de método.</span><span class="sxs-lookup"><span data-stu-id="728dd-121">Component developers should create and initialize their inputs, outputs, and custom properties during this method call.</span></span> <span data-ttu-id="728dd-122">O método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> difere de um construtor por que não é chamado toda vez que a instância de tempo de design ou a instância de tempo de execução do componente é instanciada.</span><span class="sxs-lookup"><span data-stu-id="728dd-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method differs from a constructor because it is not called every time that the design-time instance or run-time instance of the component is instantiated.</span></span>

 <span data-ttu-id="728dd-123">A implementação da classe base do método acrescenta uma entrada e uma saída ao componente e atribui a ID da entrada à propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>.</span><span class="sxs-lookup"><span data-stu-id="728dd-123">The base class implementation of the method adds an input and an output to the component and assigns the ID of the input to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property.</span></span> <span data-ttu-id="728dd-124">Porém, no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], os objetos de entrada e saída adicionados pela classe base não são nomeados.</span><span class="sxs-lookup"><span data-stu-id="728dd-124">However, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the input and output objects added by the base class are not named.</span></span> <span data-ttu-id="728dd-125">Os pacotes que contêm um componente com objetos de entrada ou saída cuja propriedade Name não está definida não são carregados com êxito.</span><span class="sxs-lookup"><span data-stu-id="728dd-125">Packages that contain a component with input or output objects whose Name property is not set will not successfully load.</span></span> <span data-ttu-id="728dd-126">Portanto, quando você usar a implementação de base, você deverá atribuir valores explicitamente à propriedade Name da entrada e saída padrão.</span><span class="sxs-lookup"><span data-stu-id="728dd-126">Therefore, when you use the base implementation, you must assign values explicitly to the Name property of the default input and output.</span></span>

```csharp
public override void ProvideComponentProperties()
{
    /// TODO: Reset the component.
    /// TODO: Add custom properties.
    /// TODO: Add input objects.
    /// TODO: Add output objects.
}
```

```vb
Public Overrides Sub ProvideComponentProperties()
    ' TODO: Reset the component.
    ' TODO: Add custom properties.
    ' TODO: Add input objects.
    ' TODO: Add output objects.
End Sub
```

### <a name="creating-custom-properties"></a><span data-ttu-id="728dd-127">Criando propriedades personalizadas</span><span class="sxs-lookup"><span data-stu-id="728dd-127">Creating Custom Properties</span></span>
 <span data-ttu-id="728dd-128">A chamada para o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> é onde os desenvolvedores de componente deveriam acrescentar propriedades personalizadas (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) ao componente.</span><span class="sxs-lookup"><span data-stu-id="728dd-128">The call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method is where component developers should add custom properties (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) to the component.</span></span> <span data-ttu-id="728dd-129">Propriedades personalizadas não têm uma propriedade de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="728dd-129">Custom properties do not have a data type property.</span></span> <span data-ttu-id="728dd-130">O tipo de dados de uma propriedade personalizada é definido pelo tipo de dados do valor que você atribui a sua propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="728dd-130">The data type of a custom property is set by the data type of the value that you assign to its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A> property.</span></span> <span data-ttu-id="728dd-131">Porém, depois que você atribuir um valor inicial à propriedade personalizada, não poderá atribuir um valor com um tipo de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="728dd-131">However, after you have assigned an initial value to the custom property, you cannot assign a value with a different data type.</span></span>

> [!NOTE]
>  <span data-ttu-id="728dd-132">A interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> tem suporte limitado para valores de propriedade do tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="728dd-132">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> interface has limited support for property values of type `Object`.</span></span> <span data-ttu-id="728dd-133">O único objeto que você pode armazenar como valor de uma propriedade personalizada é uma matriz de tipos simples, como cadeias de caracteres ou inteiros.</span><span class="sxs-lookup"><span data-stu-id="728dd-133">The only object that you can store as the value of a custom property is an array of simple types such as strings or integers.</span></span>

 <span data-ttu-id="728dd-134">Você pode indicar se sua propriedade personalizada suporta expressões de propriedade definindo o valor da sua propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> para `CPET_NOTIFY` da enumeração <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType>, conforme demonstrado no exemplo seguinte.</span><span class="sxs-lookup"><span data-stu-id="728dd-134">You can indicate that your custom property supports property expressions by setting the value of its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> property to `CPET_NOTIFY` from the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType> enumeration, as shown in the following example.</span></span> <span data-ttu-id="728dd-135">Você não tem que adicionar qualquer código para tratar ou validar a expressão de propriedade inserida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="728dd-135">You do not have to add any code to handle or to validate the property expression entered by the user.</span></span> <span data-ttu-id="728dd-136">Você pode definir um valor padrão para a propriedade, validar seu valor e ler e usar esse valor normalmente.</span><span class="sxs-lookup"><span data-stu-id="728dd-136">You can set a default value for the property, validate its value, and read and use its value normally.</span></span>

```csharp
IDTSCustomProperty100 myCustomProperty;
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY;
```

```vb
Dim myCustomProperty As IDTSCustomProperty100
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY
```

 <span data-ttu-id="728dd-137">Você pode limitar os usuários a selecionar um valor de propriedade personalizada de uma enumeração usando a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> propriedade, conforme mostrado no exemplo a seguir, que pressupõe que você definiu uma enumeração pública chamada `MyValidValues` .</span><span class="sxs-lookup"><span data-stu-id="728dd-137">You can limit users to selecting a custom property value from an enumeration by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> property, as shown in the following example, which assumes that you have defined a public enumeration named `MyValidValues`.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the type with the custom property.
customProperty.TypeConverter = typeof(MyValidValues).AssemblyQualifiedName;
// Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne;  
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the type with the custom property.
customProperty.TypeConverter = GetType(MyValidValues).AssemblyQualifiedName 
' Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne
```

 <span data-ttu-id="728dd-138">Para obter mais informações, consulte "Conversão do tipo generalizada" e "Implementando um conversor de tipo" na [Biblioteca MSDN](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="728dd-138">For more information, see "Generalized Type Conversion" and "Implementing a Type Converter" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

 <span data-ttu-id="728dd-139">Você pode especificar uma caixa de diálogo do editor personalizado para o valor da sua propriedade personalizada usando a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A>, conforme demonstrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="728dd-139">You can specify a custom editor dialog box for the value of your custom property by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property, as shown in the following example.</span></span> <span data-ttu-id="728dd-140">Em primeiro lugar, é preciso criar um editor do tipo personalizado que herde do `System.Drawing.Design.UITypeEditor`, caso você não consiga localizar uma classe de editor do tipo de interface do usuário existente adequada às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="728dd-140">First, you must create a custom type editor that inherits from `System.Drawing.Design.UITypeEditor`, if you cannot locate an existing UI type editor class that fits your needs.</span></span>

```csharp
public class MyCustomTypeEditor : UITypeEditor
{
...
}
```

```vb
Public Class MyCustomTypeEditor
  Inherits UITypeEditor 
  ...
End Class
```

 <span data-ttu-id="728dd-141">Em seguida, especifique essa classe como o valor da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> da sua propriedade personalizada.</span><span class="sxs-lookup"><span data-stu-id="728dd-141">Next, specify this class as the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property of your custom property.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the editor with the custom property.
customProperty.UITypeEditor = typeof(MyCustomTypeEditor).AssemblyQualifiedName;
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the editor with the custom property.
customProperty.UITypeEditor = GetType(MyCustomTypeEditor).AssemblyQualifiedName
```

 <span data-ttu-id="728dd-142">Para obter mais informações, consulte "Implementando um editor do tipo de interface do usuário" na [Biblioteca MSDN](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="728dd-142">For more information, see "Implementing a UI Type Editor" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

<span data-ttu-id="728dd-143">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="728dd-143">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="728dd-144">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="728dd-144">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="728dd-145">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="728dd-145">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="728dd-146">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="728dd-146">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="728dd-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="728dd-147">See Also</span></span>
 [<span data-ttu-id="728dd-148">Métodos de tempo de execução de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="728dd-148">Run-time Methods of a Data Flow Component</span></span>](run-time-methods-of-a-data-flow-component.md)


