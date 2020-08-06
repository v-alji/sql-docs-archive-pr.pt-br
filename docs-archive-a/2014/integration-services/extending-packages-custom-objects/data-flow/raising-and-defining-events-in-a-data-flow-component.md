---
title: Gerando e definindo eventos em um componente de fluxo de dados | Microsoft Docs
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
- data flow components [Integration Services], events
- events [Integration Services], custom
- custom events [Integration Services]
- custom data flow components [Integration Services], events
- events [Integration Services], raising
- predefined events [Integration Services]
ms.assetid: 1d8c5358-9384-47a8-b7cb-7b0650384119
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 25f4572f8a8af829145da4e4d685f5dddad4a29a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679437"
---
# <a name="raising-and-defining-events-in-a-data-flow-component"></a><span data-ttu-id="56572-102">Gerando e definindo eventos em um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="56572-102">Raising and Defining Events in a Data Flow Component</span></span>
  <span data-ttu-id="56572-103">Desenvolvedores de componente podem gerar um subconjunto dos eventos definidos na interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> por meio de chamada dos métodos expostos na propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="56572-103">Component developers can raise a subset of the events defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface by calling the methods exposed on the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="56572-104">Você também pode definir eventos personalizados usando a coleção <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> e gerá-los durante a execução usando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="56572-104">You can also define custom events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection, and raise them during execution by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="56572-105">Esta seção descreve como criar e gerar um evento, e fornece diretrizes sobre quando você deve gerar eventos em tempo de design.</span><span class="sxs-lookup"><span data-stu-id="56572-105">This section describes how to create and raise an event, and provides guidelines on when you should raise events at design time.</span></span>

## <a name="raising-events"></a><span data-ttu-id="56572-106">Acionar eventos</span><span class="sxs-lookup"><span data-stu-id="56572-106">Raising Events</span></span>
 <span data-ttu-id="56572-107">Os componentes acionam eventos usando os métodos **Fire\<X>** da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="56572-107">Components raise events by using the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="56572-108">Você pode gerar eventos durante o design e a execução do componente.</span><span class="sxs-lookup"><span data-stu-id="56572-108">You can raise events during component design and execution.</span></span> <span data-ttu-id="56572-109">Em geral, durante o design do componente, os métodos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> são chamados durante a validação.</span><span class="sxs-lookup"><span data-stu-id="56572-109">Typically, during component design, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> methods are called during validation.</span></span> <span data-ttu-id="56572-110">Esses eventos exibem mensagens no painel **Lista de Erros** do [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] e fornecem comentários a usuários do componente quando um componente é configurado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="56572-110">These events display messages in the **Error List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] and provide feedback to users of the component when a component is incorrectly configured.</span></span>

 <span data-ttu-id="56572-111">Os componentes também podem gerar eventos a qualquer momento durante a execução.</span><span class="sxs-lookup"><span data-stu-id="56572-111">Components can also raise events at any point during execution.</span></span> <span data-ttu-id="56572-112">Eventos permitem aos desenvolvedores de componentes fornecer comentários a usuários do componente durante sua execução.</span><span class="sxs-lookup"><span data-stu-id="56572-112">Events allow component developers to provide feedback to users of the component as it executes.</span></span> <span data-ttu-id="56572-113">É provável que a chamada do método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> durante a execução leve à falha do pacote.</span><span class="sxs-lookup"><span data-stu-id="56572-113">Calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> method during execution is likely to fail the package.</span></span>

## <a name="defining-and-raising-custom-events"></a><span data-ttu-id="56572-114">Definindo e gerando eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="56572-114">Defining and Raising Custom Events</span></span>

### <a name="defining-a-custom-event"></a><span data-ttu-id="56572-115">Definindo um evento personalizado</span><span class="sxs-lookup"><span data-stu-id="56572-115">Defining a Custom Event</span></span>
 <span data-ttu-id="56572-116">Eventos personalizados são criados chamando o método <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> da coleção <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A>.</span><span class="sxs-lookup"><span data-stu-id="56572-116">Custom events are created by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection.</span></span> <span data-ttu-id="56572-117">Esta coleção é definida pela tarefa de fluxo de dados e fornecida como uma propriedade para o desenvolvedor de componente através da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="56572-117">This collection is set by the data flow task and provided as a property to the component developer through the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="56572-118">Esta classe contém eventos personalizados definidos pela tarefa de fluxo de dados e eventos personalizados definidos pelo componente durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>.</span><span class="sxs-lookup"><span data-stu-id="56572-118">This class contains custom events defined by the data flow task and custom events defined by the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method.</span></span>

 <span data-ttu-id="56572-119">Os eventos personalizados de um componente não persistem no pacote XML.</span><span class="sxs-lookup"><span data-stu-id="56572-119">The custom events of a component are not persisted in the package XML.</span></span> <span data-ttu-id="56572-120">Portanto, o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> é chamado durante o design e a execução para permitir que o componente defina os eventos gerados por ele.</span><span class="sxs-lookup"><span data-stu-id="56572-120">Therefore, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method is called during both design and execution to allow the component to define the events it raises.</span></span>

 <span data-ttu-id="56572-121">O parâmetro *allowEventHandlers* do método <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> especifica se o componente permite criar objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> para o evento.</span><span class="sxs-lookup"><span data-stu-id="56572-121">The *allowEventHandlers* parameter of the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method specifies whether the component allows <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects to be created for the event.</span></span> <span data-ttu-id="56572-122">Observe que <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> são síncronos.</span><span class="sxs-lookup"><span data-stu-id="56572-122">Note that <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> are synchronous.</span></span> <span data-ttu-id="56572-123">Portanto, o componente não retomará a execução até que um <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> anexado ao evento personalizado termine a execução.</span><span class="sxs-lookup"><span data-stu-id="56572-123">Therefore the component does not resume execution until an <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> attached to the custom event has finished executing.</span></span> <span data-ttu-id="56572-124">Se o parâmetro *AllowEventHandlers* for `true` , cada parâmetro do evento será disponibilizado automaticamente para todos os <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objetos por meio de variáveis que são criadas e preenchidas automaticamente pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="56572-124">If the *allowEventHandlers* parameter is `true`, each parameter of the event is automatically made available to any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects through variables that are created and populated automatically by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

### <a name="raising-a-custom-event"></a><span data-ttu-id="56572-125">Gerando um evento personalizado</span><span class="sxs-lookup"><span data-stu-id="56572-125">Raising a Custom Event</span></span>
 <span data-ttu-id="56572-126">Componentes geram eventos personalizados chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> e fornecendo o nome, texto e parâmetros do evento.</span><span class="sxs-lookup"><span data-stu-id="56572-126">Components raise custom events by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method, and providing the name, text, and parameters of the event.</span></span> <span data-ttu-id="56572-127">Se o parâmetro *AllowEventHandlers* for `true` , qualquer um <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> criado para o evento personalizado será executado pelo mecanismo de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="56572-127">If the *allowEventHandlers* parameter is `true`, any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> that are created for the custom event are executed by the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] run-time engine.</span></span>

### <a name="custom-event-sample"></a><span data-ttu-id="56572-128">Exemplo de evento personalizado</span><span class="sxs-lookup"><span data-stu-id="56572-128">Custom Event Sample</span></span>
 <span data-ttu-id="56572-129">O exemplo de código a seguir mostra um componente que define um texto personalizado durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> e, depois, gera o evento em tempo de execução chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="56572-129">The following code example shows a component that defines a custom event during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method, and then raises the event at run time by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span>

```csharp
public override void RegisterEvents()
{
    string [] parameterNames = new string[2]{"RowCount", "StartTime"};
    ushort [] parameterTypes = new ushort[2]{ DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)};
    string [] parameterDescriptions = new string[2]{"The number of rows to sort.", "The start time of the Sort operation."};
    EventInfos.Add("StartingSort","Fires when the component begins sorting the rows.",false,ref parameterNames, ref parameterTypes, ref parameterDescriptions);
}
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
    while (buffer.NextRow())
    {
       // Process buffer rows.
    }

    IDTSEventInfo100 eventInfo = EventInfos["StartingSort"];
    object []arguments = new object[2]{buffer.RowCount, DateTime.Now };
    ComponentMetaData.FireCustomEvent("StartingSort", "Beginning sort operation.", ref arguments, ComponentMetaData.Name, ref FireSortEventAgain);
}
```

```vb
Public  Overrides Sub RegisterEvents() 
  Dim parameterNames As String() = New String(2) {"RowCount", "StartTime"} 
  Dim parameterTypes As System.UInt16() = New System.UInt16(2) {DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)} 
  Dim parameterDescriptions As String() = New String(2) {"The number of rows to sort.", "The start time of the Sort operation."} 
  EventInfos.Add("StartingSort", "Fires when the component begins sorting the rows.", False, parameterNames, parameterTypes, parameterDescriptions) 
End Sub 

Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
  While buffer.NextRow 
  End While 
  Dim eventInfo As IDTSEventInfo100 = EventInfos("StartingSort") 
  Dim arguments As Object() = New Object(2) {buffer.RowCount, DateTime.Now} 
  ComponentMetaData.FireCustomEvent("StartingSort", _
    "Beginning sort operation.", arguments, _
    ComponentMetaData.Name, FireSortEventAgain) 
End Sub
```

<span data-ttu-id="56572-130">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="56572-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="56572-131">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="56572-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="56572-132">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="56572-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="56572-133">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="56572-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="56572-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56572-134">See Also</span></span>
 <span data-ttu-id="56572-135">[Integration Services &#40;do SSIS&#41; manipuladores de eventos](../../integration-services-ssis-event-handlers.md) [Adicionar um manipulador de eventos a um pacote](../../add-an-event-handler-to-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="56572-135">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) [Add an Event Handler to a Package](../../add-an-event-handler-to-a-package.md)</span></span>


