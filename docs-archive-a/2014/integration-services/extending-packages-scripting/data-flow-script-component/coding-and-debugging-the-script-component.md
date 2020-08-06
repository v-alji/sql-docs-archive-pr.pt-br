---
title: Codificar e depurar o componente de Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, development environment
- Script component [Integration Services], debugging
- Script component [Integration Services], coding
- SSIS Script component, debugging
- Script component [Integration Services], development environment
- debugging [Integration Services], scripts
- SSIS Script component, coding
- VSTA
ms.assetid: c3913c15-66aa-4b61-89b5-68488fa5f0a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9363ad447ca3d0031289eafb1d8f616320fca5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575222"
---
# <a name="coding-and-debugging-the-script-component"></a><span data-ttu-id="ad702-102">Codificando e depurando o componente Script</span><span class="sxs-lookup"><span data-stu-id="ad702-102">Coding and Debugging the Script Component</span></span>
  <span data-ttu-id="ad702-103">No [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, o componente Script tem dois modos: modo de design de metadados e modo de design de código.</span><span class="sxs-lookup"><span data-stu-id="ad702-103">In [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the Script component has two modes: metadata design mode and code design mode.</span></span> <span data-ttu-id="ad702-104">Quando você abre o **Editor de Transformação Scripts**, o componente digita o modo de design de metadados no qual você configura metadados e define propriedades do componente.</span><span class="sxs-lookup"><span data-stu-id="ad702-104">When you open the **Script Transformation Editor**, the component enters metadata design mode, in which you configure metadata and set component properties.</span></span> <span data-ttu-id="ad702-105">Depois de definir as propriedades do componente Script e configurar a entrada e as saídas em modo de design de metadados, você pode alternar para o modo de design de código para gravar seu script personalizado.</span><span class="sxs-lookup"><span data-stu-id="ad702-105">After you have set the properties of the Script component and configured the input and outputs in metadata design mode, you can switch to code design mode to write your custom script.</span></span> <span data-ttu-id="ad702-106">Para obter mais informações sobre o modo de design de metadados e modo de design de código, consulte [Configurando o componente Script no Editor de Componentes de Script](configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="ad702-106">For more information about metadata design mode and code design mode, see [Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md).</span></span>

## <a name="writing-the-script-in-code-design-mode"></a><span data-ttu-id="ad702-107">Escrevendo o Script em modo de design de código</span><span class="sxs-lookup"><span data-stu-id="ad702-107">Writing the Script in Code Design Mode</span></span>

### <a name="script-component-development-environment"></a><span data-ttu-id="ad702-108">Ambiente de desenvolvimento do componente Script</span><span class="sxs-lookup"><span data-stu-id="ad702-108">Script Component Development Environment</span></span>
 <span data-ttu-id="ad702-109">Para gravar o script, clique em **Editar Script** na página **Script** do **Editor de Transformação Scripts** para abrir o IDE do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] VSTA ([!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications).</span><span class="sxs-lookup"><span data-stu-id="ad702-109">To write your script, click **Edit Script** on the **Script** page of the **Script Transformation Editor** to open the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE.</span></span> <span data-ttu-id="ad702-110">O VSTA IDE inclui todos os recursos padrão do ambiente [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].NET, como o editor [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] codificado por cores, o IntelliSense e o Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="ad702-110">The VSTA IDE includes all the standard features of the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET environment, such as the color-coded [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] editor, IntelliSense, and Object Browser.</span></span>

 <span data-ttu-id="ad702-111">O código de Script é escrito em [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic ou em [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="ad702-111">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="ad702-112">Você especifica a linguagem de script configurando a propriedade **ScriptLanguage** no **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="ad702-112">You specify the script language by setting the **ScriptLanguage** property in the **Script Transformation Editor**.</span></span> <span data-ttu-id="ad702-113">Caso prefira usar outra linguagem de programação, você pode desenvolver um assembly personalizado na linguagem de sua escolha e chamar sua funcionalidade do código no componente Script.</span><span class="sxs-lookup"><span data-stu-id="ad702-113">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script component.</span></span>

 <span data-ttu-id="ad702-114">O script criado no componente Script é armazenado na definição do pacote.</span><span class="sxs-lookup"><span data-stu-id="ad702-114">The script that you create in the Script component is stored in the package definition.</span></span> <span data-ttu-id="ad702-115">Não há arquivo de script separado.</span><span class="sxs-lookup"><span data-stu-id="ad702-115">There is no separate script file.</span></span> <span data-ttu-id="ad702-116">Portanto, o uso do componente Script não afeta a implantação do pacote.</span><span class="sxs-lookup"><span data-stu-id="ad702-116">Therefore, the use of the Script component does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="ad702-117">Enquanto você projeta o pacote, o código de script é gravado temporariamente em um arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="ad702-117">While you design the package, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="ad702-118">Como o fato de armazenar informações confidenciais em um arquivo representa um potencial risco à segurança, recomendamos não incluir informações, como senhas, no código de script.</span><span class="sxs-lookup"><span data-stu-id="ad702-118">Because storing sensitive information in a file is a potential security risk, we recommended that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="ad702-119">Por padrão, `Option Strict` fica desabilitado no IDE.</span><span class="sxs-lookup"><span data-stu-id="ad702-119">By default, `Option Strict` is disabled in the IDE.</span></span>

### <a name="script-component-project-structure"></a><span data-ttu-id="ad702-120">Estrutura do projeto do componente Script</span><span class="sxs-lookup"><span data-stu-id="ad702-120">Script Component Project Structure</span></span>
 <span data-ttu-id="ad702-121">O poder do componente Script reside em poder gerar código de infraestrutura que reduz a quantidade de códigos que você deve gravar.</span><span class="sxs-lookup"><span data-stu-id="ad702-121">The power of the Script component is that it can generate infrastructure code that reduces the amount of code that you must write.</span></span> <span data-ttu-id="ad702-122">Esse recurso se baseia no fato de que entradas e saídas e suas colunas e propriedades são fixadas e conhecidas com antecedência.</span><span class="sxs-lookup"><span data-stu-id="ad702-122">This feature relies on the fact that inputs and outputs and their columns and properties are fixed and known in advance.</span></span> <span data-ttu-id="ad702-123">Portanto, qualquer alteração subsequente que você faça nos metadados do componente poderá invalidar o código que você gravou.</span><span class="sxs-lookup"><span data-stu-id="ad702-123">Therefore, any subsequent changes that you make to the component's metadata may invalidate the code that you have written.</span></span> <span data-ttu-id="ad702-124">Isso causa erros de compilação durante a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="ad702-124">This causes compilation errors during execution of the package.</span></span>

#### <a name="project-items-and-classes-in-the-script-component-project"></a><span data-ttu-id="ad702-125">Itens e classes de projeto no projeto do componente Script</span><span class="sxs-lookup"><span data-stu-id="ad702-125">Project Items and Classes in the Script Component Project</span></span>
 <span data-ttu-id="ad702-126">Quando você alterna para o modo de design de código, o VSTA IDE abre e exibe o item de projeto `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="ad702-126">When you switch to code design mode, the VSTA IDE opens and displays the `ScriptMain` project item.</span></span> <span data-ttu-id="ad702-127">O item de projeto `ScriptMain` contém a classe `ScriptMain` editável, que serve como ponto de entrada para o script e fica onde você grava seu código.</span><span class="sxs-lookup"><span data-stu-id="ad702-127">The `ScriptMain` project item contains the editable `ScriptMain` class, which serves as the entry point for the script and which is where you write your code.</span></span> <span data-ttu-id="ad702-128">Os elementos de código na classe variam dependendo da linguagem de programação que você selecionou para a tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="ad702-128">The code elements in the class vary depending on the programming language that you selected for the Script task.</span></span>

 <span data-ttu-id="ad702-129">O projeto de script contém dois itens de projeto somente leitura adicionais gerados automaticamente:</span><span class="sxs-lookup"><span data-stu-id="ad702-129">The script project contains two additional auto-generated read-only project items:</span></span>

-   <span data-ttu-id="ad702-130">O item de projeto `ComponentWrapper` contém três classes:</span><span class="sxs-lookup"><span data-stu-id="ad702-130">The `ComponentWrapper` project item contains three classes:</span></span>

    -   <span data-ttu-id="ad702-131">A classe `UserComponent`, que herda de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> e contém os métodos e propriedades que você vai usar para processar dados e interagir com o pacote.</span><span class="sxs-lookup"><span data-stu-id="ad702-131">The `UserComponent` class, which inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> and contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="ad702-132">A classe `ScriptMain` herda da classe `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="ad702-132">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

    -   <span data-ttu-id="ad702-133">Uma classe de coleção `Connections` que contém referências às conexões selecionadas na página Gerenciador de Conexões do Editor de Transformação Scripts.</span><span class="sxs-lookup"><span data-stu-id="ad702-133">A `Connections` collection class that contains references to the connections selected on the Connection Manager page of the Script Transformation Editor.</span></span>

    -   <span data-ttu-id="ad702-134">Uma `Variables` classe de coleção que contém referências às variáveis inseridas nas `ReadOnlyVariable` `ReadWriteVariables` Propriedades e na página **script** do editor de **transformação scripts**.</span><span class="sxs-lookup"><span data-stu-id="ad702-134">A `Variables` collection class that contains references to the variables entered in the `ReadOnlyVariable` and `ReadWriteVariables` properties on the **Script** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="ad702-135">O `BufferWrapper` item de projeto contém uma classe que herda de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> para cada entrada e saída configurada na página **entradas e saídas** do **Editor de transformação scripts**.</span><span class="sxs-lookup"><span data-stu-id="ad702-135">The `BufferWrapper` project item contains a class that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output configured on the **Inputs and Outputs** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="ad702-136">Cada uma dessas classes contém propriedades de acessador digitadas que correspondem às colunas de entrada e saída configuradas e os buffers de fluxo de dados que contêm as colunas.</span><span class="sxs-lookup"><span data-stu-id="ad702-136">Each of these classes contains typed accessor properties that correspond to the configured input and output columns, and the data flow buffers that contain the columns.</span></span>

 <span data-ttu-id="ad702-137">Para obter mais informações sobre como usar esses objetos, métodos e propriedades, consulte [Compreender o Component Object Model do Script](understanding-the-script-component-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="ad702-137">For information about how to use these objects, methods, and properties, see [Understanding the Script Component Object Model](understanding-the-script-component-object-model.md).</span></span> <span data-ttu-id="ad702-138">Para obter informações sobre como usar os métodos e propriedades dessas classes em um tipo específico de componente Script, consulte a seção [Exemplos adicionais de componente de script](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="ad702-138">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="ad702-139">Os tópicos de exemplo também contêm exemplos de código completos.</span><span class="sxs-lookup"><span data-stu-id="ad702-139">The example topics also contain complete code samples.</span></span>

 <span data-ttu-id="ad702-140">Quando você configura o componente Script como uma transformação, o item de projeto `ScriptMain` contém o seguinte código gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ad702-140">When you configure the Script component as a transformation, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="ad702-141">O modelo de código também fornece uma visão geral do componente Script e informações adicionais sobre como recuperar e manipular objetos SSIS, como variáveis, eventos e conexões.</span><span class="sxs-lookup"><span data-stu-id="ad702-141">The code template also provides an overview of the Script component, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Component
' Write scripts using Microsoft Visual Basic 2008.
' ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

<Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute> _
<CLSCompliant(False)> _
Public Class ScriptMain
    Inherits UserComponent

    Public Overrides Sub PreExecute()
        MyBase.PreExecute()
        '
        ' Add your code here for preprocessing or remove if not needed
        '
    End Sub

    Public Overrides Sub PostExecute()
        MyBase.PostExecute()
        '
        ' Add your code here for postprocessing or remove if not needed
        ' You can set read/write variables here, for example:
        ' Me.Variables.MyIntVar = 100
        '
    End Sub

    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)
        '
        ' Add your code here
        '
    End Sub

End Class
```

```csharp
/* Microsoft SQL Server Integration Services user script component
*  Write scripts using Microsoft Visual C# 2008.
*  ScriptMain is the entry point class of the script.*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

[Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute]
public class ScriptMain : UserComponent
{

    public override void PreExecute()
    {
        base.PreExecute();
        /*
          Add your code here for preprocessing or remove if not needed
        */
    }

    public override void PostExecute()
    {
        base.PostExecute();
        /*
          Add your code here for postprocessing or remove if not needed
          You can set read/write variables here, for example:
          Variables.MyIntVar = 100
        */
    }

    public override void Input0_ProcessInputRow(Input0Buffer Row)
    {
        /*
          Add your code here
        */
    }

}
```

#### <a name="additional-project-items-in-the-script-component-project"></a><span data-ttu-id="ad702-142">Itens de projeto adicionais no projeto do componente Script</span><span class="sxs-lookup"><span data-stu-id="ad702-142">Additional Project Items in the Script Component Project</span></span>
 <span data-ttu-id="ad702-143">O projeto do componente Script pode incluir itens diferentes do item `ScriptMain` padrão.</span><span class="sxs-lookup"><span data-stu-id="ad702-143">The Script component project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="ad702-144">Você pode adicionar classes, módulos, arquivos de código e pastas ao projeto, e você pode usar pastas para organizar grupos de itens.</span><span class="sxs-lookup"><span data-stu-id="ad702-144">You can add classes, modules, code files, and folders to the project, and you can use folders to organize groups of items.</span></span>

 <span data-ttu-id="ad702-145">Todos os itens que você adiciona persistem dentro do pacote.</span><span class="sxs-lookup"><span data-stu-id="ad702-145">All the items that you add are persisted inside the package.</span></span>

#### <a name="references-in-the-script-component-project"></a><span data-ttu-id="ad702-146">Referências no projeto do componente Script</span><span class="sxs-lookup"><span data-stu-id="ad702-146">References in the Script Component Project</span></span>
 <span data-ttu-id="ad702-147">Você pode adicionar referências a assemblies gerenciados clicando com o botão direito do mouse no projeto da tarefa Script no **Explorador de Projeto** e clicando em **Adicionar Referência**.</span><span class="sxs-lookup"><span data-stu-id="ad702-147">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="ad702-148">Para obter mais informações, consulte [Referenciar outros assemblies em soluções de script](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="ad702-148">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="ad702-149">Você pode exibir as referências do projeto no IDE VSTA no **Modo de Exibição de Classe** ou no **Explorador de Projeto**.</span><span class="sxs-lookup"><span data-stu-id="ad702-149">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="ad702-150">É possível abrir qualquer uma dessas janelas no menu **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="ad702-150">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="ad702-151">Você pode adicionar uma referência nova no menu **Projeto**, de **Explorador de Projeto** ou de **Modo de Exibição de Classe**.</span><span class="sxs-lookup"><span data-stu-id="ad702-151">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-component"></a><span data-ttu-id="ad702-152">Interagindo com o pacote no componente Script</span><span class="sxs-lookup"><span data-stu-id="ad702-152">Interacting with the Package in the Script Component</span></span>
 <span data-ttu-id="ad702-153">O script personalizado que você grava no componente Script pode acessar e usar variáveis e gerenciadores de conexões do pacote que os contém através de acessadores de tipo mais acentuado nas classes base geradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ad702-153">The custom script that you write in the Script component can access and use variables and connection managers from the containing package through strongly-typed accessors in the auto-generated base classes.</span></span> <span data-ttu-id="ad702-154">Contudo, você deve configurar as variáveis e os gerenciadores de conexões antes de digitar o modo de design de código, se quiser disponibilizá-los para seu script.</span><span class="sxs-lookup"><span data-stu-id="ad702-154">However, you must configure both variables and connection managers before entering code-design mode if you want to make them available to your script.</span></span> <span data-ttu-id="ad702-155">Você também pode gerar eventos e executar log do código do componente Script.</span><span class="sxs-lookup"><span data-stu-id="ad702-155">You can also raise events and perform logging from your Script component code.</span></span>

 <span data-ttu-id="ad702-156">Os itens de projeto gerados automaticamente no projeto do componente Script fornecem os seguintes objetos, métodos e propriedades para interagir com o pacote.</span><span class="sxs-lookup"><span data-stu-id="ad702-156">The autogenerated project items in the Script component project provide the following objects, methods, and properties for interacting with the package.</span></span>

|<span data-ttu-id="ad702-157">Recurso do Pacote</span><span class="sxs-lookup"><span data-stu-id="ad702-157">Package Feature</span></span>|<span data-ttu-id="ad702-158">Método de Acesso</span><span class="sxs-lookup"><span data-stu-id="ad702-158">Access Method</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="ad702-159">variáveis</span><span class="sxs-lookup"><span data-stu-id="ad702-159">Variables</span></span>|<span data-ttu-id="ad702-160">Use as propriedades nomeadas e digitadas do acessador na classe de coleção `Variables` no item de projeto `ComponentWrapper`, expostas através da propriedade `Variables` da classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="ad702-160">Use the named and typed accessor properties in the `Variables` collection class in the `ComponentWrapper` project item, exposed through the `Variables` property of the `ScriptMain` class.</span></span><br /><br /> <span data-ttu-id="ad702-161">O método `PreExecute` só pode acessar variáveis somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ad702-161">The `PreExecute` method can access only read-only variables.</span></span> <span data-ttu-id="ad702-162">O método `PostExecute` pode acessar variáveis somente leitura e de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="ad702-162">The `PostExecute` method can access both read-only and read/write variables.</span></span>|
|<span data-ttu-id="ad702-163">conexões</span><span class="sxs-lookup"><span data-stu-id="ad702-163">Connections</span></span>|<span data-ttu-id="ad702-164">Use as propriedades nomeadas e digitadas do acessador na classe de coleção `Connections` no item de projeto `ComponentWrapper`, expostas através da propriedade `Connections` da classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="ad702-164">Use the named and typed accessor properties in the `Connections` collection class in the `ComponentWrapper` project item, exposed through the `Connections` property of the `ScriptMain` class.</span></span>|
|<span data-ttu-id="ad702-165">Eventos</span><span class="sxs-lookup"><span data-stu-id="ad702-165">Events</span></span>|<span data-ttu-id="ad702-166">Gere eventos usando a <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> propriedade da `ScriptMain` classe e os métodos \*\*Fire \<X> \*\* da <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span><span class="sxs-lookup"><span data-stu-id="ad702-166">Raise events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class and the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span>|
|<span data-ttu-id="ad702-167">Registro em log</span><span class="sxs-lookup"><span data-stu-id="ad702-167">Logging</span></span>|<span data-ttu-id="ad702-168">Execute o registro em log usando o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> da classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="ad702-168">Perform logging by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class.</span></span>|

## <a name="debugging-the-script-component"></a><span data-ttu-id="ad702-169">Depurando o componente Script</span><span class="sxs-lookup"><span data-stu-id="ad702-169">Debugging the Script Component</span></span>
 <span data-ttu-id="ad702-170">Para depurar o código no seu componente Script, defina pelo menos um ponto de interrupção no código e, depois, feche o VSTA IDE para executar o pacote no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad702-170">To debug the code in your Script component, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ad702-171">Quando a execução do pacote insere o componente Script, o VSTA IDE é reaberto e exibe seu código em modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ad702-171">When package execution enters the Script component, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="ad702-172">Depois que a execução atingir seu ponto de interrupção, você poderá examinar valores de variáveis e passar pelo código restante.</span><span class="sxs-lookup"><span data-stu-id="ad702-172">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!NOTE]
>  <span data-ttu-id="ad702-173">Você não pode depurar um componente Script quando executa-o como parte de um pacote filho que é executado a partir de uma tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="ad702-173">You cannot debug a Script component when you run the Script component as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="ad702-174">Nessas circunstâncias, os pontos de interrupção definidos no componente Script no pacote filho são desconsiderados.</span><span class="sxs-lookup"><span data-stu-id="ad702-174">Breakpoints that you set in the Script component in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="ad702-175">Você pode depurar o pacote filho normalmente, executando-o separadamente.</span><span class="sxs-lookup"><span data-stu-id="ad702-175">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="ad702-176">Quando você depura um pacote que contém vários componentes Script, o depurador depura um componente Script.</span><span class="sxs-lookup"><span data-stu-id="ad702-176">When you debug a package that contains multiple Script components, the debugger debugs one Script component.</span></span> <span data-ttu-id="ad702-177">O sistema poderá depurar outro componente Script se o depurador for concluído, como no caso de um contêiner Loop Foreach ou Loop For.</span><span class="sxs-lookup"><span data-stu-id="ad702-177">The system can debug another Script component if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

 <span data-ttu-id="ad702-178">Você também pode monitorar a execução do componente Script usando os métodos seguintes:</span><span class="sxs-lookup"><span data-stu-id="ad702-178">You can also monitor the execution of the Script component by using the following methods:</span></span>

-   <span data-ttu-id="ad702-179">Interrompa a execução e exiba uma mensagem modal usando o `MessageBox.Show` método no namespace **System. Windows. Forms** .</span><span class="sxs-lookup"><span data-stu-id="ad702-179">Interrupt execution and display a modal message by using the `MessageBox.Show` method in the **System.Windows.Forms** namespace.</span></span> <span data-ttu-id="ad702-180">(Remova esse código após concluir o processo de depuração).</span><span class="sxs-lookup"><span data-stu-id="ad702-180">(Remove this code after you complete the debugging process.)</span></span>

-   <span data-ttu-id="ad702-181">Gere eventos para mensagens informativas, advertências e erros.</span><span class="sxs-lookup"><span data-stu-id="ad702-181">Raise events for informational messages, warnings, and errors.</span></span> <span data-ttu-id="ad702-182">Os métodos FireInformation, FireWarning e FireError exibem a descrição do evento na janela de **Saída** do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ad702-182">The FireInformation, FireWarning, and FireError methods display the event description in the Visual Studio **Output** window.</span></span> <span data-ttu-id="ad702-183">No entanto, o método FireProgress, o método Console.Write e o método Console.WriteLine não exibem nenhuma informação na janela de **Saída**.</span><span class="sxs-lookup"><span data-stu-id="ad702-183">However, the FireProgress method, the Console.Write method, and Console.WriteLine method do not display any information in the **Output** window.</span></span> <span data-ttu-id="ad702-184">Mensagens do evento FireProgress aparecem na guia **Progresso** do Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad702-184">Messages from the FireProgress event appear on the **Progress** tab of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="ad702-185">Para obter mais informações, consulte [Acionando eventos no componente Script](../../data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="ad702-185">For more information, see [Raising Events in the Script Component](../../data-flow/transformations/script-component.md).</span></span>

-   <span data-ttu-id="ad702-186">Eventos de log ou mensagens definidas pelo usuário para provedores de log habilitados.</span><span class="sxs-lookup"><span data-stu-id="ad702-186">Log events or user-defined messages to enabled logging providers.</span></span> <span data-ttu-id="ad702-187">Para obter mais informações, consulte [Registro em log no componente Script](logging-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="ad702-187">For more information, see [Logging in the Script Component](logging-in-the-script-component.md).</span></span>

 <span data-ttu-id="ad702-188">Caso queira apenas examinar a saída de um componente Script configurado como uma origem ou uma transformação, sem salvar os dados em um destino, você pode parar o fluxo de dados com uma [Transformação de Contagem de Linhas](../../data-flow/transformations/row-count-transformation.md) e anexar um visualizador de dados à saída do componente Script.</span><span class="sxs-lookup"><span data-stu-id="ad702-188">If you just want to examine the output of a Script component configured as a source or as a transformation, without saving the data to a destination, you can stop the data flow with a [Row Count Transformation](../../data-flow/transformations/row-count-transformation.md) and attach a data viewer to the output of the Script component.</span></span> <span data-ttu-id="ad702-189">Para obter informações sobre visualizadores de dados, consulte [Depurar o fluxo de dados](../../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="ad702-189">For information about data viewers, see [Debugging Data Flow](../../troubleshooting/debugging-data-flow.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ad702-190">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ad702-190">In This Section</span></span>
 <span data-ttu-id="ad702-191">Para obter mais informações sobre como codificar o componente Script, consulte os tópicos seguintes nesta seção.</span><span class="sxs-lookup"><span data-stu-id="ad702-191">For more information about coding the Script component, see the following topics in this section.</span></span>

 <span data-ttu-id="ad702-192">[Noções básicas sobre o Script Component Object Model](understanding-the-script-component-object-model.md) Explica como usar os objetos, métodos e propriedades disponíveis no componente Script.</span><span class="sxs-lookup"><span data-stu-id="ad702-192">[Understanding the Script Component Object Model](understanding-the-script-component-object-model.md) Explains how to use the objects, methods, and properties available in the Script component.</span></span>

 <span data-ttu-id="ad702-193">[Fazendo referência a outros assemblies em soluções de script](../referencing-other-assemblies-in-scripting-solutions.md) Explica como fazer referência a objetos da [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] biblioteca de classes no componente Script.</span><span class="sxs-lookup"><span data-stu-id="ad702-193">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) Explains how to reference objects from the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library in the Script component.</span></span>

 <span data-ttu-id="ad702-194">[Simulando uma saída de erro para o componente Script](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explica como simular uma saída de erro para linhas que geram erros durante o processamento pelo componente Script.</span><span class="sxs-lookup"><span data-stu-id="ad702-194">[Simulating an Error Output for the Script Component](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explains how to simulate an error output for rows that raise errors during processing by the Script component.</span></span>

## <a name="external-resources"></a><span data-ttu-id="ad702-195">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="ad702-195">External Resources</span></span>

-   <span data-ttu-id="ad702-196">Entrada de blog, [Problemas de instalação e configuração de VSTA nas instalações de SSIS 2008 e R2](https://go.microsoft.com/fwlink/?LinkId=215661), em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="ad702-196">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="ad702-197">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ad702-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ad702-198">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="ad702-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ad702-199">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="ad702-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ad702-200">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="ad702-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad702-201">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ad702-201">See Also</span></span>
 [<span data-ttu-id="ad702-202">Configurar o componente de Script no Editor de Componentes de Script</span><span class="sxs-lookup"><span data-stu-id="ad702-202">Configuring the Script Component in the Script Component Editor</span></span>](configuring-the-script-component-in-the-script-component-editor.md)


