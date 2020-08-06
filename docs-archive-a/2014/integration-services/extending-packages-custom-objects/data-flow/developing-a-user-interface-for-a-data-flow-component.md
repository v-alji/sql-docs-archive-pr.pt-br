---
title: Desenvolvendo uma interface do usuário para um componente de fluxo de dados | Microsoft Docs
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
- data flow components [Integration Services], custom editors
- user interfaces [Integration Services]
- custom data flow components [Integration Services], custom editors
- custom component editors [Integration Services]
- IDtsComponentUI interface
- UITypeName property
- custom user interface [Integration Services], custom data flow component
- editors [Integration Services]
ms.assetid: 10b829a1-609b-42e3-9070-cfe5a2bb698c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f97f21ad14a5fa67fb49192931a0cb46d0cb41da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679448"
---
# <a name="developing-a-user-interface-for-a-data-flow-component"></a><span data-ttu-id="a43c9-102">Desenvolvendo uma interface do usuário para um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="a43c9-102">Developing a User Interface for a Data Flow Component</span></span>
  <span data-ttu-id="a43c9-103">Os desenvolvedores de componentes podem fornecer uma interface de usuário personalizada para um componente, que é exibida no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] quando o componente é editado.</span><span class="sxs-lookup"><span data-stu-id="a43c9-103">Component developers can provide a custom user interface for a component, which is displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] when the component is edited.</span></span> <span data-ttu-id="a43c9-104">A implementação de uma interface de usuário personalizada fornece a você uma notificação quando o componente é adicionado a ou excluído de uma tarefa de fluxo de dados, e quando é solicitada ajuda para o componente.</span><span class="sxs-lookup"><span data-stu-id="a43c9-104">Implementing a custom user interface provides you with notification when the component is added to or deleted from a data flow task, and when help is requested for the component.</span></span>

 <span data-ttu-id="a43c9-105">Se você não fornecer uma interface de usuário personalizada para seu componente, os usuários ainda poderão configurar o componente e suas propriedades personalizadas utilizando o Editor Avançado.</span><span class="sxs-lookup"><span data-stu-id="a43c9-105">If you do not provide a custom user interface for your component, users can still configure the component and its custom properties by using the Advanced Editor.</span></span> <span data-ttu-id="a43c9-106">Para certificar-se de que o Editor Avançado permita aos usuários editar valores de propriedade personalizados adequadamente, utilize as propriedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="a43c9-106">You can ensure that the Advanced Editor allows users to edit custom property values appropriately by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> properties of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> when appropriate.</span></span> <span data-ttu-id="a43c9-107">Para obter mais informações, consulte "Criando propriedades personalizadas" em [Métodos de tempo de design de um componente de fluxo de dados](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a43c9-107">For more information, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>

## <a name="setting-the-uitypename-property"></a><span data-ttu-id="a43c9-108">Definindo a propriedade UITypeName</span><span class="sxs-lookup"><span data-stu-id="a43c9-108">Setting the UITypeName Property</span></span>
 <span data-ttu-id="a43c9-109">Para fornecer uma interface de usuário personalizada, o desenvolvedor deve definir a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> como o nome de uma classe que implementa a interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="a43c9-109">To provide a custom user interface, the developer must set the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> to the name of a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="a43c9-110">Quando essa propriedade é definida pelo componente, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] carrega e chama a interface do usuário personalizada quando o componente é editado no Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a43c9-110">When this property is set by the component, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] loads and calls the custom user interface when the component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="a43c9-111">A propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> é uma cadeia de caracteres delimitada por vírgulas que identifica o nome totalmente qualificado do tipo.</span><span class="sxs-lookup"><span data-stu-id="a43c9-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property is a comma-delimited string that identifies the fully qualified name of the type.</span></span> <span data-ttu-id="a43c9-112">A lista a seguir mostra, em ordem, os elementos que identificam o tipo:</span><span class="sxs-lookup"><span data-stu-id="a43c9-112">The following list shows, in order, the elements that identify the type:</span></span>

-   <span data-ttu-id="a43c9-113">Nome do tipo</span><span class="sxs-lookup"><span data-stu-id="a43c9-113">Type name</span></span>

-   <span data-ttu-id="a43c9-114">Nome do assembly</span><span class="sxs-lookup"><span data-stu-id="a43c9-114">Assembly name</span></span>

-   <span data-ttu-id="a43c9-115">Versão do arquivo</span><span class="sxs-lookup"><span data-stu-id="a43c9-115">File version</span></span>

-   <span data-ttu-id="a43c9-116">Cultura</span><span class="sxs-lookup"><span data-stu-id="a43c9-116">Culture</span></span>

-   <span data-ttu-id="a43c9-117">Token de chave pública</span><span class="sxs-lookup"><span data-stu-id="a43c9-117">Public key token</span></span>

 <span data-ttu-id="a43c9-118">O exemplo de código a seguir mostra uma classe que deriva da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> e especifica a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A>.</span><span class="sxs-lookup"><span data-stu-id="a43c9-118">The following code example shows a class that derives from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class and specifies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property.</span></span>

```csharp
[DtsPipelineComponent(
DisplayName="SampleComponent",
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...",
ComponentType = ComponentType.Transform)]
public class SampleComponent : PipelineComponent
{
//TODO: Implement the component here.
}
```

```vb
<DtsPipelineComponent(DisplayName="SampleComponent", _
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...", ComponentType=ComponentType.Transform)> _ 
Public Class SampleComponent 
 Inherits PipelineComponent 
End Class
```

## <a name="implementing-the-idtscomponentui-interface"></a><span data-ttu-id="a43c9-119">Implementando a interface IDtsComponentUI</span><span class="sxs-lookup"><span data-stu-id="a43c9-119">Implementing the IDtsComponentUI Interface</span></span>
 <span data-ttu-id="a43c9-120">A interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> contém métodos que o Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] chama quando um componente é adicionado, excluído e editado.</span><span class="sxs-lookup"><span data-stu-id="a43c9-120">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface contains methods that [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls when a component is added, deleted, and edited.</span></span> <span data-ttu-id="a43c9-121">Desenvolvedores de componente podem fornecer código na sua implementação desses métodos para interagir com usuários do componente.</span><span class="sxs-lookup"><span data-stu-id="a43c9-121">Component developers can provide code in their implementation of these methods to interact with users of the component.</span></span>

 <span data-ttu-id="a43c9-122">Essa classe costuma ser implementada em um assembly separado do próprio componente.</span><span class="sxs-lookup"><span data-stu-id="a43c9-122">This class is typically implemented in an assembly separate from the component itself.</span></span> <span data-ttu-id="a43c9-123">Embora o uso de um assembly separado não seja exigido, isso permite ao desenvolvedor criar e empregar o componente e a interface de usuário separadamente, e mantém a superfície binária do componente pequena.</span><span class="sxs-lookup"><span data-stu-id="a43c9-123">Although use of a separate assembly is not required, this lets the developer build and deploy the component and the user interface independently of each other, and keeps the binary footprint of the component small.</span></span>

 <span data-ttu-id="a43c9-124">A implementação de uma interface de usuário personalizada dá ao desenvolvedor de componente mais controle sobre o componente pois ele é editado no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a43c9-124">Implementing a custom user interface gives the component developer more control over the component as it is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a43c9-125">Por exemplo, um componente pode adicionar código ao método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A>, que é chamado quando um componente é inicialmente adicionado a uma tarefa de fluxo de dados, e exibir um assistente que orienta o usuário na configuração inicial do componente.</span><span class="sxs-lookup"><span data-stu-id="a43c9-125">For example, a component can add code to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> method, which is called when a component is initially added to a data flow task, and display a wizard that guides the user through the initial configuration of the component.</span></span>

 <span data-ttu-id="a43c9-126">Após criar uma classe que implementa a interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>, adicione código para responder à interação do usuário com o componente.</span><span class="sxs-lookup"><span data-stu-id="a43c9-126">After you have created a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, you must add code to respond to user interaction with the component.</span></span> <span data-ttu-id="a43c9-127">O método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> fornece a interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> do componente e é chamado antes dos métodos <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="a43c9-127">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component, and is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> methods.</span></span> <span data-ttu-id="a43c9-128">Essa referência deve ser armazenada em uma variável de membro particular e usada para modificar metadados do componente depois disso.</span><span class="sxs-lookup"><span data-stu-id="a43c9-128">This reference should be stored in a private member variable and used to modify the component's metadata thereafter.</span></span>

## <a name="modifying-a-component-and-persisting-changes"></a><span data-ttu-id="a43c9-129">Modificando um componente e mantendo alterações</span><span class="sxs-lookup"><span data-stu-id="a43c9-129">Modifying a Component and Persisting Changes</span></span>
 <span data-ttu-id="a43c9-130">A interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> é fornecida como um parâmetro ao método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="a43c9-130">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface is provided as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method.</span></span> <span data-ttu-id="a43c9-131">Essa referência deve ser armazenada em cache em uma variável de membro pelo código de interface de usuário e, depois, usada para modificar o componente em resposta à interação do usuário com a interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="a43c9-131">This reference should be cached in a member variable by the user interface code, and then used to modify the component in response to user interaction with the user interface.</span></span>

 <span data-ttu-id="a43c9-132">Embora você possa modificar o componente diretamente através da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, é melhor criar uma instância do <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> utilizando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a43c9-132">Although you can modify the component directly through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, it is better to create an instance of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method.</span></span> <span data-ttu-id="a43c9-133">Quando você edita o componente diretamente através da interface, ignora as garantias de validação dele.</span><span class="sxs-lookup"><span data-stu-id="a43c9-133">When you edit the component directly by using the interface, you bypass the component's validation safeguards.</span></span> <span data-ttu-id="a43c9-134">A vantagem de utilizar a instância de tempo de design do componente através do <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> é que você garante o controle pelo componente das alterações feitas nele.</span><span class="sxs-lookup"><span data-stu-id="a43c9-134">The advantage of using the design-time instance of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> is that you ensure that the component has control over the changes made to it.</span></span>

 <span data-ttu-id="a43c9-135">O valor de retorno do método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> determina se alterações feitas em um componente são mantidas ou descartadas.</span><span class="sxs-lookup"><span data-stu-id="a43c9-135">The return value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method determines whether changes made to a component are persisted or discarded.</span></span> <span data-ttu-id="a43c9-136">Quando esse método retorna `false`, todas as alterações são descartadas; o `true` mantém as alterações no componente e marca o pacote que deve ser salvo.</span><span class="sxs-lookup"><span data-stu-id="a43c9-136">When this method returns `false`, all changes are discarded; `true` persists the changes to the component and marks the package as needing to be saved.</span></span>

### <a name="using-the-services-of-the-ssis-designer"></a><span data-ttu-id="a43c9-137">Usando os serviços do Designer SSIS</span><span class="sxs-lookup"><span data-stu-id="a43c9-137">Using the Services of the SSIS Designer</span></span>
 <span data-ttu-id="a43c9-138">O parâmetro `IServiceProvider` do método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> fornece acesso aos seguintes serviços do Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a43c9-138">The `IServiceProvider` parameter of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides access to the following services of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer:</span></span>

|<span data-ttu-id="a43c9-139">Serviço</span><span class="sxs-lookup"><span data-stu-id="a43c9-139">Service</span></span>|<span data-ttu-id="a43c9-140">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a43c9-140">Description</span></span>|
|-------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsClipboardService>|<span data-ttu-id="a43c9-141">Usado para determinar se o componente foi gerado como parte de uma operação copiar/colar ou recortar/colar.</span><span class="sxs-lookup"><span data-stu-id="a43c9-141">Used to determine whether the component was generated as part of a copy/paste or cut/paste operation.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionService>|<span data-ttu-id="a43c9-142">Usado acessar conexões existentes ou criar novas conexões no pacote.</span><span class="sxs-lookup"><span data-stu-id="a43c9-142">Used to access existing connections or to create new connections in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IErrorCollectionService>|<span data-ttu-id="a43c9-143">Usado para capturar eventos de componentes de fluxo de dados quando você precisa capturar todos os erros e avisos levantados pelo componente, em vez de receber apenas o último erro ou aviso.</span><span class="sxs-lookup"><span data-stu-id="a43c9-143">Used to capture events from data flow components when you need to capture all the errors and warnings raised by the component instead of receiving only the last error or warning.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsVariableService>|<span data-ttu-id="a43c9-144">Usado para acessar variáveis existentes ou criar novas variáveis no pacote.</span><span class="sxs-lookup"><span data-stu-id="a43c9-144">Used to access existing variables or to create new variables in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsPipelineEnvironmentService>|<span data-ttu-id="a43c9-145">Usado por componentes de fluxo de dados para acessar a tarefa Fluxo de Dados pai e outros componentes no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a43c9-145">Used by data flow components to access the parent Data Flow task and other components in the data flow.</span></span> <span data-ttu-id="a43c9-146">Esse recurso pode ser usado para desenvolver um componente como o Assistente para Dimensões de Alteração Lenta, que cria e conecta componentes de fluxo de dados adicionais, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="a43c9-146">This feature could be used to develop a component like the Slowly Changing Dimension Wizard that creates and connects additional data flow components as needed.</span></span>|

 <span data-ttu-id="a43c9-147">Esses serviços oferecem aos desenvolvedores de componente a capacidade de acessar e criar objetos no pacote no qual o componente é carregado.</span><span class="sxs-lookup"><span data-stu-id="a43c9-147">These services provide component developers the ability to access and create objects in the package in which the component is loaded.</span></span>

## <a name="sample"></a><span data-ttu-id="a43c9-148">Amostra</span><span class="sxs-lookup"><span data-stu-id="a43c9-148">Sample</span></span>
 <span data-ttu-id="a43c9-149">O exemplo de código a seguir mostra a integração de uma classe de interface do usuário personalizada que implementa a interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>, e um formulário do Windows que serve como o editor de um componente.</span><span class="sxs-lookup"><span data-stu-id="a43c9-149">The following code example shows the integration of a custom user interface class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, and a Windows form that serves as the editor for a component.</span></span>

### <a name="custom-user-interface-class"></a><span data-ttu-id="a43c9-150">Classe de interface do usuário personalizada</span><span class="sxs-lookup"><span data-stu-id="a43c9-150">Custom User Interface Class</span></span>
 <span data-ttu-id="a43c9-151">O código a seguir mostra a classe que implementa a interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="a43c9-151">The following code shows the class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="a43c9-152">O método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> cria o editor de componente e, depois, exibe o formulário.</span><span class="sxs-lookup"><span data-stu-id="a43c9-152">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method creates the component editor and then displays the form.</span></span> <span data-ttu-id="a43c9-153">O valor de retorno do formulário determina se as alterações do componente são mantidas.</span><span class="sxs-lookup"><span data-stu-id="a43c9-153">The return value of the form determines whether changes to the component are persisted.</span></span>

```csharp
using System;
using System.Windows.Forms;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Pipeline.Design;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    public class SampleComponentUI : IDtsComponentUI
    {
        IDTSComponentMetaData100 md;
        IServiceProvider sp;

        public void Help(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void New(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void Delete(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Variables vars, Connections cons)
        {
            // Create and display the form for the user interface.
            SampleComponentUIForm componentEditor = new SampleComponentUIForm(cons, vars, md);

            DialogResult result  = componentEditor.ShowDialog(parentWindow);

            if (result == DialogResult.OK)
                return true;

            return false;
        }
        public void Initialize(IDTSComponentMetaData100 dtsComponentMetadata, IServiceProvider serviceProvider)
        {
            // Store the component metadata.
            this.md = dtsComponentMetadata;
        }
    }
}
```

```vb
Imports System 
Imports System.Windows.Forms 
Imports Microsoft.SqlServer.Dts.Runtime 
Imports Microsoft.SqlServer.Dts.Pipeline.Design 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Class SampleComponentUI 
 Implements IDtsComponentUI 
   Private md As IDTSComponentMetaData100 
   Private sp As IServiceProvider 

   Public Sub Help(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub New(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub Delete(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal vars As Variables, ByVal cons As Connections) As Boolean 
     ' Create and display the form for the user interface.
     Dim componentEditor As SampleComponentUIForm = New SampleComponentUIForm(cons, vars, md) 
     Dim result As DialogResult = componentEditor.ShowDialog(parentWindow) 
     If result = DialogResult.OK Then 
       Return True 
     End If 
     Return False 
   End Function 

   Public Sub Initialize(ByVal dtsComponentMetadata As IDTSComponentMetaData100, ByVal serviceProvider As IServiceProvider) 
     Me.md = dtsComponentMetadata 
   End Sub 
 End Class 

End Namespace
```

### <a name="custom-editor"></a><span data-ttu-id="a43c9-154">Editor personalizado</span><span class="sxs-lookup"><span data-stu-id="a43c9-154">Custom Editor</span></span>
 <span data-ttu-id="a43c9-155">O código a seguir mostra a implementação do formulário do Windows que é mostrado durante a chamada ao método <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="a43c9-155">The following code shows the implementation of the Windows form that is shown during the call to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method.</span></span>

```csharp
using System;
using System.Drawing;
using System.Collections;
using System.ComponentModel;
using System.Windows.Forms;
using System.Data;

using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    public partial class SampleComponentUIForm : System.Windows.Forms.Form
    {
        private Connections connections;
        private Variables variables;
        private IDTSComponentMetaData100 metaData;
        private CManagedComponentWrapper designTimeInstance;
        private System.ComponentModel.IContainer components = null;

        public SampleComponentUIForm( Connections cons, Variables vars, IDTSComponentMetaData100 md)
        {
            variables = vars;
            connections = cons;
            metaData = md;
        }

        private void btnOk_Click(object sender, System.EventArgs e)
        {
            if (designTimeInstance == null)
                designTimeInstance = metaData.Instantiate();

            designTimeInstance.SetComponentProperty( "CustomProperty", txtCustomPropertyValue.Text);

            this.Close();
        }

        private void btnCancel_Click(object sender, System.EventArgs e)
        {
            this.Close();
        }
    }
}
```

```vb
Imports System 
Imports System.Drawing 
Imports System.Collections 
Imports System.ComponentModel 
Imports System.Windows.Forms 
Imports System.Data 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Partial Class SampleComponentUIForm 
  Inherits System.Windows.Forms.Form 
   Private connections As Connections 
   Private variables As Variables 
   Private metaData As IDTSComponentMetaData100 
   Private designTimeInstance As CManagedComponentWrapper 
   Private components As System.ComponentModel.IContainer = Nothing 

   Public Sub New(ByVal cons As Connections, ByVal vars As Variables, ByVal md As IDTSComponentMetaData100) 
     variables = vars 
     connections = cons 
     metaData = md 
   End Sub 

   Private Sub btnOk_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     If designTimeInstance Is Nothing Then 
       designTimeInstance = metaData.Instantiate 
     End If 
     designTimeInstance.SetComponentProperty("CustomProperty", txtCustomPropertyValue.Text) 
     Me.Close 
   End Sub 

   Private Sub btnCancel_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     Me.Close 
   End Sub 
 End Class 

End Namespace
```

<span data-ttu-id="a43c9-156">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a43c9-156">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a43c9-157">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="a43c9-157">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a43c9-158">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="a43c9-158">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a43c9-159">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="a43c9-159">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a43c9-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a43c9-160">See Also</span></span>
 [<span data-ttu-id="a43c9-161">Criando um componente de fluxo de dados personalizado</span><span class="sxs-lookup"><span data-stu-id="a43c9-161">Creating a Custom Data Flow Component</span></span>](creating-a-custom-data-flow-component.md)


