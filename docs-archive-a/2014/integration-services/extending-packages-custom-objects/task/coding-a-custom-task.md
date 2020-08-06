---
title: Codificando uma tarefa personalizada | Microsoft Docs
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
- Validate method
- custom tasks [Integration Services], validating
- validation [Integration Services], design-time tasks
- SSIS custom tasks, validating
ms.assetid: dc224f4f-b339-4eb6-a008-1b4fe0ea4fd2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c369f4a7e8352be7ddde9e2e3938b47b0bcc1349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575228"
---
# <a name="coding-a-custom-task"></a><span data-ttu-id="366cb-102">Codificando uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="366cb-102">Coding a Custom Task</span></span>
  <span data-ttu-id="366cb-103">Depois de criar uma classe que herda da classe base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) e aplicar o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> a essa classe, você deve substituir a implementação das propriedades e dos métodos da classe base para fornecer a funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="366cb-103">After you have created a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>

## <a name="configuring-the-task"></a><span data-ttu-id="366cb-104">Configurando a tarefa</span><span class="sxs-lookup"><span data-stu-id="366cb-104">Configuring the Task</span></span>

### <a name="validating-the-task"></a><span data-ttu-id="366cb-105">Validando a tarefa</span><span class="sxs-lookup"><span data-stu-id="366cb-105">Validating the Task</span></span>
 <span data-ttu-id="366cb-106">Ao projetar um pacote do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], você pode usar a validação para verificar as definições de cada tarefa, de forma a detectar definições incorretas ou inadequadas tão logo sejam definidas, em vez de encontrar todos os erros somente em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-106">When you are designing an [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package, you can use validation to verify settings on each task, so that you can catch incorrect or inappropriate settings as soon as they are set, instead of finding all errors at run-time only.</span></span> <span data-ttu-id="366cb-107">O propósito da validação é determinar se a tarefa contém configurações ou conexões inválidas que a impedirão de ser executada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="366cb-107">The purpose of validation is to determine whether the task contains invalid settings or connections that will prevent it from running successfully.</span></span> <span data-ttu-id="366cb-108">Isso garante que o pacote contenha tarefas com boa chance de serem executadas na primeira execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-108">This makes sure that the package contains tasks that have a good chance of running on their first run.</span></span>

 <span data-ttu-id="366cb-109">Você pode implementar a validação usando o método `Validate` em código personalizado.</span><span class="sxs-lookup"><span data-stu-id="366cb-109">You can implement validation by using the `Validate` method in custom code.</span></span> <span data-ttu-id="366cb-110">O mecanismo de tempo de execução valida uma tarefa chamando o método `Validate` na tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-110">The run-time engine validates a task by calling the `Validate` method on the task.</span></span> <span data-ttu-id="366cb-111">É responsabilidade do desenvolvedor da tarefa definir os critérios que lhe proporcionem uma validação bem sucedida ou malsucedida da tarefa, e notificar o mecanismo de tempo de execução do resultado dessa avaliação.</span><span class="sxs-lookup"><span data-stu-id="366cb-111">It is the responsibility of the task developer to define the criteria that give you a successful or failed task validation, and to notify the run-time engine of the result of this evaluation.</span></span>

#### <a name="task-abstract-base-class"></a><span data-ttu-id="366cb-112">Classe base abstrata da tarefa</span><span class="sxs-lookup"><span data-stu-id="366cb-112">Task Abstract Base Class</span></span>
 <span data-ttu-id="366cb-113">A classe base abstrata [Microsoft. SqlServer. Dts. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) contém o `Validate` método que cada tarefa substitui para definir seus critérios de validação.</span><span class="sxs-lookup"><span data-stu-id="366cb-113">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) abstract base class provides the `Validate` method that each task overrides to define its validation criteria.</span></span> <span data-ttu-id="366cb-114">O [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer chama automaticamente o método `Validate` várias vezes durante o projeto do pacote, e fornece indicações visuais ao usuário quando ocorrem avisos ou erros para ajudar a identificar problemas com a configuração da tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-114">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer automatically calls the `Validate` method multiple times during package design, and provides visual cues to the user when warnings or errors occur to help identify problems with the configuration of the task.</span></span> <span data-ttu-id="366cb-115">As tarefas fornecem resultados de validação retornando um valor da enumeração <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> e gerando eventos de aviso e erro.</span><span class="sxs-lookup"><span data-stu-id="366cb-115">Tasks provide validation results by returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and by raising warning and error events.</span></span> <span data-ttu-id="366cb-116">Esses eventos contêm informações que são exibidas ao usuário no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="366cb-116">These events contain information that is displayed to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="366cb-117">Seguem alguns exemplos de validação:</span><span class="sxs-lookup"><span data-stu-id="366cb-117">Some examples for validation follow:</span></span>

-   <span data-ttu-id="366cb-118">Um gerenciador de conexões valida o nome do arquivo específico.</span><span class="sxs-lookup"><span data-stu-id="366cb-118">A connection manager validates the specific file name.</span></span>

-   <span data-ttu-id="366cb-119">Um gerenciador de conexões valida que o tipo de entrada é o tipo esperado, como um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="366cb-119">A connection manager validates that the type of input is the expected type, such as an XML file.</span></span>

-   <span data-ttu-id="366cb-120">Uma tarefa que aguarda a entrada de banco de dados verifica se não pode receber dados de uma conexão que não seja de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="366cb-120">A task that expects database input verifies that it cannot receive data from a non-database connection.</span></span>

-   <span data-ttu-id="366cb-121">Uma tarefa garante que nenhuma de suas propriedades contradiga outras propriedades definidas na mesma tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-121">A task guarantees that none of its properties contradicts other properties set on the same task.</span></span>

-   <span data-ttu-id="366cb-122">Uma tarefa garante que todos os recursos necessários usados pela tarefa em tempo de execução estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="366cb-122">A task guarantees that all required resources used by the task at execution time are available.</span></span>

 <span data-ttu-id="366cb-123">Desempenho é algo a ser considerado ao determinar o que é validado e o que não é.</span><span class="sxs-lookup"><span data-stu-id="366cb-123">Performance is something to consider in determining what is validated and what is not.</span></span> <span data-ttu-id="366cb-124">Por exemplo, a entrada para uma tarefa pode ser uma conexão em uma rede que tem baixa largura de banda ou alto tráfego.</span><span class="sxs-lookup"><span data-stu-id="366cb-124">For example, the input to a task might be a connection over a network that has low bandwidth or heavy traffic.</span></span> <span data-ttu-id="366cb-125">A validação poderá levar vários segundos para ser processada se você decidir validar se o recurso está disponível.</span><span class="sxs-lookup"><span data-stu-id="366cb-125">The validation may take several seconds to process if you decide to validate that the resource is available.</span></span> <span data-ttu-id="366cb-126">Outra validação pode causar uma viagem de ida e volta para um servidor que está em demanda alta e a rotina de validação pode ficar lenta.</span><span class="sxs-lookup"><span data-stu-id="366cb-126">Another validation may cause a round-trip to a server that is in high demand, and the validation routine might be slow.</span></span> <span data-ttu-id="366cb-127">Embora existam muitas propriedades e configurações que podem ser validadas, nem tudo deve ser validado.</span><span class="sxs-lookup"><span data-stu-id="366cb-127">Although there are many properties and settings that can be validated, not everything should be validated.</span></span>

-   <span data-ttu-id="366cb-128">O código no método `Validate` também é chamado pelo <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> antes de a tarefa ser executada e o <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> cancela a execução se a validação falhar.</span><span class="sxs-lookup"><span data-stu-id="366cb-128">The code in the `Validate` method is also called by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> before the task is run, and the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> cancels execution if validation fails.</span></span>

#### <a name="user-interface-considerations-during-validation"></a><span data-ttu-id="366cb-129">Considerações da interface do usuário durante a validação</span><span class="sxs-lookup"><span data-stu-id="366cb-129">User Interface Considerations during Validation</span></span>
 <span data-ttu-id="366cb-130">O [Microsoft. SqlServer. Dts. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) inclui uma <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface como um parâmetro para o `Validate` método.</span><span class="sxs-lookup"><span data-stu-id="366cb-130">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) includes an <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface as a parameter to the `Validate` method.</span></span> <span data-ttu-id="366cb-131">A interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> contém os métodos que são chamados pela tarefa para gerar eventos para o mecanismo de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-131">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the methods that are called by the task in order to raise events to the run-time engine.</span></span> <span data-ttu-id="366cb-132">Os métodos <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> são chamados quando uma condição de aviso ou erro ocorre durante a validação.</span><span class="sxs-lookup"><span data-stu-id="366cb-132">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods are called when a warning or error condition occurs during validation.</span></span> <span data-ttu-id="366cb-133">Ambos os métodos de aviso requerem os mesmos parâmetros, que incluem um código de erro, um componente de origem, descrição, arquivo de Ajuda e informações de contexto da Ajuda.</span><span class="sxs-lookup"><span data-stu-id="366cb-133">Both warning methods require the same parameters, which include an error code, source component, description, Help file, and Help context information.</span></span> <span data-ttu-id="366cb-134">O [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer usa essas informações para exibir indicações visuais na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="366cb-134">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses this information to display visual cues on the design surface.</span></span> <span data-ttu-id="366cb-135">As indicações visuais fornecidas pelo designer incluem um ícone de exclamação que aparece próximo à tarefa na superfície do designer.</span><span class="sxs-lookup"><span data-stu-id="366cb-135">The visual cues that are provided by the designer include an exclamation icon that appears next to the task on the designer surface.</span></span> <span data-ttu-id="366cb-136">Essa indicação visual sinaliza ao usuário que a tarefa requer configuração adicional antes de continuar a execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-136">This visual cue signals to the user that the task requires additional configuration before execution can continue.</span></span>

 <span data-ttu-id="366cb-137">O ícone de exclamação também exibe uma dica de ferramenta que contém uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="366cb-137">The exclamation icon also displays a ToolTip that contains an error message.</span></span> <span data-ttu-id="366cb-138">A mensagem de erro é fornecida pela tarefa no parâmetro de descrição do evento.</span><span class="sxs-lookup"><span data-stu-id="366cb-138">The error message is provided by the task in the description parameter of the event.</span></span> <span data-ttu-id="366cb-139">Mensagens de erro também são exibidas no painel **Lista de Tarefas** do [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], fornecendo ao usuário um local central para exibir todos os erros de validação.</span><span class="sxs-lookup"><span data-stu-id="366cb-139">Error messages are also displayed in the **Task List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], providing the user with a central location for viewing all validation errors.</span></span>

#### <a name="validation-example"></a><span data-ttu-id="366cb-140">Exemplo de validação</span><span class="sxs-lookup"><span data-stu-id="366cb-140">Validation Example</span></span>
 <span data-ttu-id="366cb-141">O exemplo de código seguinte mostra uma tarefa com uma propriedade `UserName`.</span><span class="sxs-lookup"><span data-stu-id="366cb-141">The following code example shows a task with a `UserName` property.</span></span> <span data-ttu-id="366cb-142">Essa propriedade foi especificada conforme solicitado para a validação ter sucesso.</span><span class="sxs-lookup"><span data-stu-id="366cb-142">This property has been specified as required for validation to succeed.</span></span> <span data-ttu-id="366cb-143">Se a propriedade não for definida, a tarefa postará um erro e retornará <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> da enumeração <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="366cb-143">If the property is not set, the task posts an error, and returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span> <span data-ttu-id="366cb-144">O método `Validate` é quebrado em um bloco de prova/captura e abandona a validação se ocorre uma exceção.</span><span class="sxs-lookup"><span data-stu-id="366cb-144">The `Validate` method is wrapped in a try/catch block, and fails validation if an exception occurs.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string userName = "";

  public override DTSExecResult Validate(Connections connections,
     VariableDispenser variableDispenser, IDTSComponentEvents events,
     IDTSLogging log)
  {
    try
    {
      if (this.userName == "")
      {
        //   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0);
        //   Fail validation.
        return DTSExecResult.Failure;
      }
      //   Return success.
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string UserName
  {
    get
    {
      return this.userName;
    }
    set
    {
      this.userName = value;
    }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _userName As String = ""

  Public Overrides Function Validate(ByVal connections As Connections, _
     ByVal variableDispenser As VariableDispenser, _
     ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging) As DTSExecResult

    Try
      If Me._userName = "" Then
        '   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0)
        '   Fail validation.
        Return DTSExecResult.Failure
      End If
      '   Return success.
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property UserName() As String
    Get
      Return Me._userName
    End Get
    Set(ByVal Value As String)
      Me._userName = Value
    End Set
  End Property

End Class
```

### <a name="persisting-the-task"></a><span data-ttu-id="366cb-145">Persistindo a tarefa</span><span class="sxs-lookup"><span data-stu-id="366cb-145">Persisting the Task</span></span>
 <span data-ttu-id="366cb-146">Normalmente, não é preciso implementar uma persistência personalizada para uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-146">Ordinarily you do not have to implement custom persistence for a task.</span></span> <span data-ttu-id="366cb-147">A persistência personalizada é necessária somente quando as propriedades de um objeto usam tipos de dados complexos.</span><span class="sxs-lookup"><span data-stu-id="366cb-147">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="366cb-148">Para obter mais informações, consulte [Desenvolvendo objetos personalizados para o Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="366cb-148">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>

## <a name="executing-the-task"></a><span data-ttu-id="366cb-149">Executando a tarefa</span><span class="sxs-lookup"><span data-stu-id="366cb-149">Executing the Task</span></span>
 <span data-ttu-id="366cb-150">Esta seção descreve como usar o método `Execute`, que é herdado e substituído por tarefas.</span><span class="sxs-lookup"><span data-stu-id="366cb-150">This section describes how to use the `Execute` method that is inherited and overridden by tasks.</span></span> <span data-ttu-id="366cb-151">Esta seção também explica vários modos de fornecer informações sobre os resultados da execução de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-151">This section also explains various ways of providing information about the results of task execution.</span></span>

### <a name="execute-method"></a><span data-ttu-id="366cb-152">Método Execute</span><span class="sxs-lookup"><span data-stu-id="366cb-152">Execute Method</span></span>
 <span data-ttu-id="366cb-153">As tarefas contidas em um pacote são executadas quando o runtime do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] chama seu método `Execute`.</span><span class="sxs-lookup"><span data-stu-id="366cb-153">Tasks that are contained in a package run when the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime calls their `Execute` method.</span></span> <span data-ttu-id="366cb-154">As tarefas implementam sua lógica de negócios e funcionalidade principais nesse método e fornecem os resultados da execução postando mensagens, retornando um valor da <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeração e substituindo a propriedade `get` da `ExecutionValue` propriedade.</span><span class="sxs-lookup"><span data-stu-id="366cb-154">Tasks implement their core business logic and functionality in this method, and provide the results of execution by posting messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and overriding the property `get` of the `ExecutionValue` property.</span></span>

 <span data-ttu-id="366cb-155">A classe base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) fornece uma implementação padrão do método <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="366cb-155">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class provides a default implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="366cb-156">As tarefas personalizadas anulam esse método para definir sua funcionalidade de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-156">The custom tasks override this method to define their run-time functionality.</span></span> <span data-ttu-id="366cb-157">O objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> quebra a tarefa, isolando-a do mecanismo de tempo de execução e dos outros objetos no pacote.</span><span class="sxs-lookup"><span data-stu-id="366cb-157">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object wraps the task, isolating it from the run-time engine and the other objects in the package.</span></span> <span data-ttu-id="366cb-158">Por causa desse isolamento, a tarefa não reconhece sua localização no pacote quanto à ordem de execução e é executada somente quando chamada pelo runtime.</span><span class="sxs-lookup"><span data-stu-id="366cb-158">Because of this isolation, the task is unaware of its location in the package with regard to its execution order, and runs only when it is called by the runtime.</span></span> <span data-ttu-id="366cb-159">Essa arquitetura evita os problemas que podem ocorrer quando as tarefas modificam o pacote durante a execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-159">This architecture prevents problems that can occur when tasks modify the package during execution.</span></span> <span data-ttu-id="366cb-160">A tarefa recebe acesso aos outros objetos do pacote somente por meio dos objetos fornecidos a ela como parâmetros no método <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="366cb-160">The task is provided access to the other objects in the package only through the objects supplied to it as parameters in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="366cb-161">Esses parâmetros permitem que as tarefas gerem eventos, gravem entradas no log de eventos, acessem a coleção de variáveis e inscrevam conexões em fontes de dados nas transações, ao mesmo tempo mantendo o isolamento necessário para garantir a estabilidade e a confiabilidade do pacote.</span><span class="sxs-lookup"><span data-stu-id="366cb-161">These parameters let tasks raise events, write entries to the event log, access the variables collection, and enlist connections to data sources in transactions, while still maintaining the isolation that is necessary to guarantee the stability and reliability of the package.</span></span>

 <span data-ttu-id="366cb-162">A tabela seguinte lista os parâmetros fornecidos à tarefa no método <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="366cb-162">The following table lists the parameters provided to the task in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>

|<span data-ttu-id="366cb-163">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="366cb-163">Parameter</span></span>|<span data-ttu-id="366cb-164">Descrição</span><span class="sxs-lookup"><span data-stu-id="366cb-164">Description</span></span>|
|---------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Runtime.Connections>|<span data-ttu-id="366cb-165">Contém uma coleção de objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> disponíveis para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-165">Contains a collection of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects available to the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.VariableDispenser>|<span data-ttu-id="366cb-166">Contém as variáveis disponíveis para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-166">Contains the variables available to the task.</span></span> <span data-ttu-id="366cb-167">As tarefas usam variáveis pelo VariableDispenser; as tarefas não usam variáveis diretamente.</span><span class="sxs-lookup"><span data-stu-id="366cb-167">The tasks use variables through the VariableDispenser; the tasks do not use variables directly.</span></span> <span data-ttu-id="366cb-168">O VariableDispenser bloqueia e desbloqueia as variáveis e impede deadlocks ou substituições.</span><span class="sxs-lookup"><span data-stu-id="366cb-168">The variable dispenser locks and unlocks variables, and prevents deadlocks or overwrites.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>|<span data-ttu-id="366cb-169">Contém os métodos chamados pela tarefa para gerar eventos ao mecanismo de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-169">Contains the methods called by the task to raise events to the run-time engine.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSLogging>|<span data-ttu-id="366cb-170">Contém métodos e propriedades usados pela tarefa para gravar entradas no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="366cb-170">Contains methods and properties used by the task to write entries to the event log.</span></span>|
|<span data-ttu-id="366cb-171">Objeto</span><span class="sxs-lookup"><span data-stu-id="366cb-171">Object</span></span>|<span data-ttu-id="366cb-172">Contém o objeto de transação do qual o contêiner faz parte, se houver.</span><span class="sxs-lookup"><span data-stu-id="366cb-172">Contains the transaction object that the container is a part of, if any.</span></span> <span data-ttu-id="366cb-173">Esse valor é passado como um parâmetro ao método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> de um objeto <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="366cb-173">This value is passed as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object.</span></span>|

### <a name="providing-execution-feedback"></a><span data-ttu-id="366cb-174">Fornecendo comentários de execução</span><span class="sxs-lookup"><span data-stu-id="366cb-174">Providing Execution Feedback</span></span>
 <span data-ttu-id="366cb-175">As tarefas quebram seu código em blocos `try/catch` para evitar que sejam geradas exceções ao mecanismo de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-175">Tasks wrap their code in `try/catch` blocks to prevent exceptions from being raised to the run-time engine.</span></span> <span data-ttu-id="366cb-176">Isso assegura que o pacote conclua a execução e não pare inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="366cb-176">This ensures that the package finishes execution and does not stop unexpectedly.</span></span> <span data-ttu-id="366cb-177">Porém, o mecanismo de tempo de execução fornece outros mecanismos para tratar condições de erro que podem ocorrer durante a execução de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-177">However, the run-time engine provides other mechanisms for handling error conditions that can occur during the execution of a task.</span></span> <span data-ttu-id="366cb-178">Eles incluem postar mensagens de erro e de aviso, retornar um valor da estrutura do <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, postar mensagens, retornar o valor <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> e divulgar informações sobre os resultados da execução da tarefa através da propriedade <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="366cb-178">These include posting error and warning messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> structure, posting messages, returning the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value, and disclosing information about the results of task execution through the <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A> property.</span></span>

 <span data-ttu-id="366cb-179">A interface do <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> contém os métodos <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>, que podem ser chamados pela tarefa para postar mensagens de erro e de aviso para o mecanismo de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-179">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods, which can be called by the task to post error and warning messages to the run-time engine.</span></span> <span data-ttu-id="366cb-180">Ambos os métodos requerem parâmetros como código de erro, componente de origem, descrição, arquivo de Ajuda e informações de contexto de ajuda.</span><span class="sxs-lookup"><span data-stu-id="366cb-180">Both methods require parameters such as the error code, source component, description, Help file, and help context information.</span></span> <span data-ttu-id="366cb-181">Dependendo da configuração da tarefa, o runtime responde a essas mensagens gerando eventos e pontos de interrupção, ou gravando informações no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="366cb-181">Depending on the configuration of the task, the runtime responds to these messages by raising events and breakpoints, or by writing information to the event log.</span></span>

 <span data-ttu-id="366cb-182">O <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> também fornece a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> que pode ser usada para fornecer informações adicionais sobre os resultados da execução.</span><span class="sxs-lookup"><span data-stu-id="366cb-182">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> also provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property that can be used to provide additional information about the results of execution.</span></span> <span data-ttu-id="366cb-183">Por exemplo, se uma tarefa exclui linhas de uma tabela como parte do seu método `Execute`, ela pode retornar o número de linhas excluídas como o valor da propriedade <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="366cb-183">For example, if a task deletes rows from a table as part of its `Execute` method, it might return the number of rows deleted as the value of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property.</span></span> <span data-ttu-id="366cb-184">Além disso, o <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> fornece a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A>.</span><span class="sxs-lookup"><span data-stu-id="366cb-184">In addition, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A> property.</span></span> <span data-ttu-id="366cb-185">Essa propriedade permite que o usuário mapeie o <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> retornado da tarefa para qualquer variável visível à tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-185">This property lets the user map the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> returned from the task to any variable visible to the task.</span></span> <span data-ttu-id="366cb-186">A variável especificada pode ser usada para estabelecer restrições de precedência entre as tarefas.</span><span class="sxs-lookup"><span data-stu-id="366cb-186">The specified variable can then be used to establish precedence constraints between tasks.</span></span>

### <a name="execution-example"></a><span data-ttu-id="366cb-187">Exemplo de execução</span><span class="sxs-lookup"><span data-stu-id="366cb-187">Execution Example</span></span>
 <span data-ttu-id="366cb-188">O exemplo de código seguinte demonstra uma implementação do método `Execute` e mostra uma propriedade `ExecutionValue` substituída.</span><span class="sxs-lookup"><span data-stu-id="366cb-188">The following code example demonstrates an implementation of the `Execute` method, and shows an overridden `ExecutionValue` property.</span></span> <span data-ttu-id="366cb-189">A tarefa exclui o arquivo que é especificado pela propriedade `fileName` da tarefa.</span><span class="sxs-lookup"><span data-stu-id="366cb-189">The task deletes the file that is specified by the `fileName` property of the task.</span></span> <span data-ttu-id="366cb-190">A tarefa posta um aviso se o arquivo não existir ou se a propriedade `fileName` for uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="366cb-190">The task posts a warning if the file does not exist, or if the `fileName` property is an empty string.</span></span> <span data-ttu-id="366cb-191">A tarefa retorna um valor `Boolean` na propriedade <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> para indicar se o arquivo foi excluído.</span><span class="sxs-lookup"><span data-stu-id="366cb-191">The task returns a `Boolean` value in the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property to indicate whether the file was deleted.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string fileName = "";
  private bool fileDeleted = false;

  public override DTSExecResult Execute(Connections cons,
     VariableDispenser vars, IDTSComponentEvents events,
     IDTSLogging log, Object txn)
  {
    try
    {
      if (this.fileName == "")
      {
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0);
        this.fileDeleted = false;
      }
      else
      {
        if (System.IO.File.Exists(this.fileName))
        {
          System.IO.File.Delete(this.fileName);
          this.fileDeleted = true;
        }
        else
          this.fileDeleted = false;
      }
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string FileName
  {
    get { return this.fileName; }
    set { this.fileName = value; }
  }
  public override object ExecutionValue
  {
    get { return this.fileDeleted; }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _fileName As String = ""
  Private _fileDeleted As Boolean = False

  Public Overrides Function Execute(ByVal cons As Connections, _
     ByVal vars As VariableDispenser, ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging, ByVal txn As Object) As DTSExecResult

    Try
      If Me._fileName = "" Then
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0)
        Me._fileDeleted = False
      Else
        If System.IO.File.Exists(Me._fileName) Then
          System.IO.File.Delete(Me._fileName)
          Me._fileDeleted = True
        Else
          Me._fileDeleted = False
        End If
      End If
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property FileName() As String
    Get
      Return Me._fileName
    End Get
    Set(ByVal Value As String)
      Me._fileName = Value
    End Set
  End Property

  Public Overrides ReadOnly Property ExecutionValue() As Object
    Get
      Return Me._fileDeleted
    End Get
  End Property

End Class
```

<span data-ttu-id="366cb-192">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="366cb-192">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="366cb-193">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="366cb-193">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="366cb-194">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="366cb-194">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="366cb-195">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="366cb-195">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="366cb-196">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="366cb-196">See Also</span></span>
 <span data-ttu-id="366cb-197">[Criando uma tarefa personalizada](creating-a-custom-task.md) que [codifica uma tarefa personalizada](coding-a-custom-task.md) que [desenvolve uma interface do usuário para uma tarefa personalizada](developing-a-user-interface-for-a-custom-task.md)</span><span class="sxs-lookup"><span data-stu-id="366cb-197">[Creating a Custom Task](creating-a-custom-task.md) [Coding a Custom Task](coding-a-custom-task.md) [Developing a User Interface for a Custom Task](developing-a-user-interface-for-a-custom-task.md)</span></span>


