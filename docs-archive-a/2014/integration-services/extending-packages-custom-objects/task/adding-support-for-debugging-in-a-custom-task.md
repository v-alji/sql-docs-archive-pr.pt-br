---
title: Adicionar suporte para depuração em uma tarefa personalizada | Microsoft Docs
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
- BreakpointManager class
- breakpoints [Integration Services]
- custom tasks [Integration Services], debugging
- IDTSSuspend interface
- IDTSBreakpointSite interface
- SSIS custom tasks, debugging
- debugging [Integration Services], custom tasks
ms.assetid: 7f06e49b-0b60-4e81-97da-d32dc248264a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcc1d0c18cd559b547eadb9c1fa77e8f143389d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575231"
---
# <a name="adding-support-for-debugging-in-a-custom-task"></a><span data-ttu-id="a7cd4-102">Adicionando suporte para depurando em uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="a7cd4-102">Adding Support for Debugging in a Custom Task</span></span>
  <span data-ttu-id="a7cd4-103">O mecanismo de tempo de execução [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] permite a suspensão de pacotes, tarefas e outros tipos de contêineres durante a execução usando pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine enables packages, tasks, and other types of containers to be suspended during execution by using breakpoints.</span></span> <span data-ttu-id="a7cd4-104">O uso de pontos de interrupção permite que você analise e corrija erros que impedem a execução adequada de seu aplicativo ou de tarefas.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-104">The use of breakpoints lets you review and correct errors that prevent your application or tasks from running correctly.</span></span> <span data-ttu-id="a7cd4-105">A arquitetura de ponto de interrupção permite ao cliente avaliar o valor do tempo de execução de objetos no pacote em pontos definidos da execução enquanto o processamento da tarefa fica suspenso.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-105">The breakpoint architecture enables the client to evaluate the run-time value of objects in the package at defined points of execution while task processing is suspended.</span></span>  
  
 <span data-ttu-id="a7cd4-106">Desenvolvedores de tarefa personalizada podem usar essa arquitetura para criar destinos de ponto de interrupção personalizados através da interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite>, e de sua interface pai, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-106">Custom task developers can use this architecture to create custom breakpoint targets by using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its parent interface, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span></span> <span data-ttu-id="a7cd4-107">A interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> define a interação entre o mecanismo de tempo de execução e a tarefa para criar e gerenciar sites ou destinos de ponto de interrupção personalizados.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-107">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines the interaction between the run-time engine and the task for creating and managing custom breakpoint sites or targets.</span></span> <span data-ttu-id="a7cd4-108">A interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> fornece métodos e propriedades que são chamadas pelo mecanismo de tempo de execução para notificar a tarefa para suspender ou retomar sua execução.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-108">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface provides methods and properties that are called by the run-time engine to notify the task to suspend or resume its execution.</span></span>  
  
 <span data-ttu-id="a7cd4-109">Um site ou destino de ponto de interrupção é um ponto na execução da tarefa onde o processamento pode ser suspenso.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-109">A breakpoint site or target is a point in the execution of the task where processing can be suspended.</span></span> <span data-ttu-id="a7cd4-110">Usuários selecionam entre os sites de ponto de interrupção disponíveis na caixa de diálogo **Definir Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-110">Users select from available breakpoint sites in the **Set Breakpoints** dialog box.</span></span> <span data-ttu-id="a7cd4-111">Por exemplo, além das opções de ponto de interrupção padrão, o Contêiner do Loop Foreach oferece a opção "Quebra no início de cada iteração do loop".</span><span class="sxs-lookup"><span data-stu-id="a7cd4-111">For example, in addition to the default breakpoint options, the Foreach Loop Container offers the "Break at the beginning of every iteration of the loop" option.</span></span>  
  
 <span data-ttu-id="a7cd4-112">Quando uma tarefa alcança um destino de ponto de interrupção durante a execução, ela avalia esse destino para determinar se um ponto de interrupção está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-112">When a task reaches a breakpoint target during execution, it evaluates the breakpoint target to determine whether a breakpoint is enabled.</span></span> <span data-ttu-id="a7cd4-113">Isso indica que o usuário deseja parar a execução nesse ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-113">This indicates that the user wants execution to stop at that breakpoint.</span></span> <span data-ttu-id="a7cd4-114">Se o ponto de interrupção estiver habilitado, a tarefa gerará o evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> para o mecanismo de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-114">If the breakpoint is enabled, the task raises the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event to the run-time engine.</span></span> <span data-ttu-id="a7cd4-115">O mecanismo de tempo de execução responde ao evento chamando o método `Suspend` de cada tarefa que está em execução no momento no pacote.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-115">The run-time engine responds to the event by calling the `Suspend` method of each task that is currently running in the package.</span></span> <span data-ttu-id="a7cd4-116">A execução da tarefa retoma quando o runtime chama o método `ResumeExecution` da tarefa suspensa.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-116">Execution of the task resumes when the runtime calls the `ResumeExecution` method of the suspended task.</span></span>  
  
 <span data-ttu-id="a7cd4-117">As tarefas que não usam pontos de interrupção ainda devem implementar as interfaces <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> e <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-117">Tasks that do not use breakpoints should still implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interfaces.</span></span> <span data-ttu-id="a7cd4-118">Isso garante que a tarefa será suspensa corretamente quando outros objetos do pacote gerarem eventos <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-118">This ensures that the task is suspended correctly when other objects in the package raise <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> events.</span></span>  
  
## <a name="idtsbreakpointsite-interface-and-breakpointmanager"></a><span data-ttu-id="a7cd4-119">Interface IDTSBreakpointSite e BreakpointManager</span><span class="sxs-lookup"><span data-stu-id="a7cd4-119">IDTSBreakpointSite Interface and BreakpointManager</span></span>  
 <span data-ttu-id="a7cd4-120">As tarefas criam destinos de ponto de interrupção chamando o método <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, fornecendo uma ID de inteiro e uma descrição de cadeia de caracteres como parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-120">Tasks create breakpoint targets by calling the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, providing an integer ID and string description as parameters.</span></span> <span data-ttu-id="a7cd4-121">Quando a tarefa atinge o ponto em seu código que contém um destino de ponto de interrupção, ela avalia o destino de ponto de interrupção usando o método <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> para determinar se esse ponto de interrupção está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-121">When the task reaches the point in its code that contains a breakpoint target, it evaluates the breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> method to determine whether that breakpoint is enabled.</span></span> <span data-ttu-id="a7cd4-122">Se `true`, a tarefa notifica o mecanismo de tempo de execução, gerando o evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-122">If `true`, the task notifies the run-time engine by raising the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event.</span></span>  
  
 <span data-ttu-id="a7cd4-123">A interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> define um único método, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, que é chamado pelo mecanismo de tempo de execução durante a criação da tarefa.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-123">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines a single method, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, which is called by the run-time engine during task creation.</span></span> <span data-ttu-id="a7cd4-124">Esse método fornece como parâmetro o objeto <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, que é usado então pela tarefa para criar e gerenciar seus pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-124">This method provides as a parameter the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> object, which is then used by the task to create and manage its breakpoints.</span></span> <span data-ttu-id="a7cd4-125">As tarefas devem armazenar o <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> localmente para uso durante os métodos `Validate` e `Execute`.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-125">Tasks should store the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> locally for use during the `Validate` and `Execute` methods.</span></span>  
  
 <span data-ttu-id="a7cd4-126">O exemplo de código a seguir demonstra como criar um destino de ponto de interrupção através do <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-126">The following sample code demonstrates how to create a breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span></span> <span data-ttu-id="a7cd4-127">O exemplo chama o método <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> para gerar o evento.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-127">The sample calls the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> method to raise the event.</span></span>  
  
```csharp  
public void AcceptBreakpointManager( BreakpointManager breakPointManager )  
{  
   //   Store the breakpoint manager locally.  
   this.bpm  = breakPointManager;  
}  
public override DTSExecResult Execute( Connections connections,  
  Variables variables, IDTSComponentEvents events,  
  IDTSLogging log, DtsTransaction txn)  
{  
   //   Create a breakpoint.  
   this.bpm.CreateBreakPointTarget( 1 , "A sample breakpoint target." );  
...  
   if( this.bpm.IsBreakpointTargetEnabled( 1 ) == true )  
      events.OnBreakpointHit( this.bpm.GetBreakpointTarget( 1 ) );  
}  
```  
  
```vb  
Public Sub AcceptBreakpointManager(ByVal breakPointManager As BreakpointManager)  
  
   ' Store the breakpoint manager locally.  
   Me.bpm  = breakPointManager  
  
End Sub  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
  ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
  ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' Create a breakpoint.  
   Me.bpm.CreateBreakPointTarget(1 , "A sample breakpoint target.")  
  
   If Me.bpm.IsBreakpointTargetEnabled(1) = True Then  
      events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(1))  
   End If  
  
End Function  
```  
  
## <a name="idtssuspend-interface"></a><span data-ttu-id="a7cd4-128">Interface IDTSSuspend</span><span class="sxs-lookup"><span data-stu-id="a7cd4-128">IDTSSuspend Interface</span></span>  
 <span data-ttu-id="a7cd4-129">A interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> define os métodos que são chamados pelo mecanismo de tempo de execução quando ele pausa ou retoma a execução de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-129">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface defines the methods that are called by the run-time engine when it pauses or resumes execution of a task.</span></span> <span data-ttu-id="a7cd4-130">A interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> é implementada pela interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> e seus métodos `Suspend` e `ResumeExecution` costumam ser substituídos pela tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-130">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface is implemented by the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its `Suspend` and `ResumeExecution` methods are usually overridden by the custom task.</span></span> <span data-ttu-id="a7cd4-131">Quando o mecanismo de tempo de execução recebe um evento `OnBreakpointHit` de uma tarefa, ele chama o método `Suspend` de cada tarefa em execução, notificando as tarefas que elas devem pausar.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-131">When the run-time engine receives an `OnBreakpointHit` event from a task, it calls the `Suspend` method of each running task, notifying the tasks to pause.</span></span> <span data-ttu-id="a7cd4-132">Quando o cliente retoma a execução, o mecanismo de tempo de execução chama o método `ResumeExecution` das tarefas que são suspensas.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-132">When the client resumes execution, the run-time engine calls the `ResumeExecution` method of the tasks that are suspended.</span></span>  
  
 <span data-ttu-id="a7cd4-133">A suspensão e a continuação da execução de tarefas envolvem a pausa e a continuação do thread de execução da tarefa.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-133">Suspending and resuming task execution involves pausing and resuming the task's execution thread.</span></span> <span data-ttu-id="a7cd4-134">Em código gerenciado, você faz isso usando a classe `ManualResetEvent` no namespace `System.Threading` do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-134">In managed code, you do this using the `ManualResetEvent` class in `System.Threading` namespace of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a7cd4-135">O exemplo de código a seguir demonstra a suspensão e a continuação da execução da tarefa.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-135">The following code sample demonstrates suspension and resumption of task execution.</span></span> <span data-ttu-id="a7cd4-136">Observe que o método `Execute` foi alterado do exemplo de código anterior, e o thread de execução foi pausado ao acionar o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-136">Notice that the `Execute` method has changed from the previous code sample, and the execution thread is paused when firing the breakpoint.</span></span>  
  
```csharp  
private ManualResetEvent m_suspended = new ManualResetEvent( true );  
private ManualResetEvent m_canExecute = new ManualResetEvent( true );  
private int   m_suspendRequired = 0;  
private int   m_debugMode = 0;  
  
public override DTSExecResult Execute( Connections connections, Variables variables, IDTSComponentEvents events, IDTSLogging log, DtsTransaction txn)  
{  
   // While a task is not executing, it is suspended.    
   // Now that we are executing,  
   // change to not suspended.  
   ChangeEvent(m_suspended, false);  
  
   // Check for a suspend before doing any work,   
   // in case the suspend and execute calls  
   // were initiated at virtually the same time.  
   CheckAndSuspend();  
   CheckAndFireBreakpoint( componentEvents, 1);  
}  
private void CheckAndSuspend()  
{  
   // Loop until we can execute.    
   // The loop is required rather than a simple If  
   // because there is a time between the return from WaitOne and the  
   // reset that we might receive another Suspend call.    
   // Suspend() will see that we are suspended  
   // and return.  So we need to rewait.  
   while (!m_canExecute.WaitOne(0, false))  
   {  
      ChangeEvent(m_suspended, true);  
      m_canExecute.WaitOne();  
      ChangeEvent(m_suspended, false);  
   }  
}  
private void CheckAndFireBreakpoint(IDTSComponentEvents events, int breakpointID)  
{  
   // If the breakpoint is enabled, fire it.  
   if (m_debugMode != 0 &&    this.bpm.IsBreakpointTargetEnabled(breakpointID))  
   {  
      //   Enter a suspend mode before firing the breakpoint.    
      //   Firing the breakpoint will cause the runtime   
      //   to call Suspend on this task.    
      //   Because we are blocked on the breakpoint,   
      //   we are suspended.  
      ChangeEvent(m_suspended, true);  
      events.OnBreakpointHit(this.bpm.GetBreakpointTarget(breakpointID));  
      ChangeEvent(m_suspended, false);  
   }  
   // Check for a suspension for two reasons:   
   //   1. If we are at a point where we could fire a breakpoint,   
   //      we are at a valid suspend point.  Even if we didn't hit a  
   //      breakpoint, the runtime may have called suspend,   
   //      so check for it.       
   //   2. Between the return from OnBreakpointHit   
   //      and the reset of the event, it is possible to have  
   //      received a suspend call from which we returned because   
   //      we were already suspended.  We need to be sure it is okay  
   //      to continue executing now.  
   CheckAndSuspend();  
}  
static void ChangeEvent(ManualResetEvent e, bool shouldSet)  
{  
   bool succeeded;  
   if (shouldSet)  
      succeeded = e.Set();  
   else  
      succeeded = e.Reset();  
  
   if (!succeeded)  
      throw new Exception("Synchronization object failed.");  
  
}  
public bool SuspendRequired  
{  
   get   {return m_suspendRequired != 0;}  
   set  
   {  
      // This lock is also taken by Suspend().    
      // Because it is possible for the package to be  
      // suspended and resumed in quick succession,   
      // this property might be set before  
      // the actual Suspend() call.    
      // Without the lock, the Suspend() might reset the canExecute  
      // event after we set it to abort the suspension.  
      lock (this)  
      {  
         Interlocked.Exchange(ref m_suspendRequired, value ? 1 : 0);  
         if (!value)  
            ResumeExecution();  
      }  
   }  
}  
public void ResumeExecution()  
{  
   ChangeEvent( m_canExecute,true );  
}  
public void Suspend()  
{  
   // This lock is also taken by the set SuspendRequired method.    
   // It prevents this call from overriding an   
   // aborted suspension.  See comments in set SuspendRequired.  
   lock (this)  
   {  
      // If a Suspend is required, do it.  
      if (m_suspendRequired != 0)  
         ChangeEvent(m_canExecute, false);  
   }  
   // We can't return from Suspend until the task is "suspended".  
   // This can happen one of two ways:   
   // the m_suspended event occurs, indicating that the execute thread  
   // has suspended, or the canExecute flag is set,   
   // indicating that a suspend is no longer required.  
   WaitHandle [] suspendOperationComplete = {m_suspended, m_canExecute};  
   WaitHandle.WaitAny(suspendOperationComplete);  
}  
```  
  
```vb  
Private m_suspended As ManualResetEvent = New ManualResetEvent(True)  
Private m_canExecute As ManualResetEvent = New ManualResetEvent(True)  
Private m_suspendRequired As Integer = 0  
Private m_debugMode As Integer = 0  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' While a task is not executing it is suspended.    
   ' Now that we are executing,  
   ' change to not suspended.  
   ChangeEvent(m_suspended, False)  
  
   ' Check for a suspend before doing any work,   
   ' in case the suspend and execute calls  
   ' were initiated at virtually the same time.  
   CheckAndSuspend()  
   CheckAndFireBreakpoint(componentEvents, 1)  
  
End Function  
  
Private Sub CheckAndSuspend()  
  
   ' Loop until we can execute.    
   ' The loop is required rather than a simple if  
   ' because there is a time between the return from WaitOne and the  
   ' reset that we might receive another Suspend call.    
   ' Suspend() will see that we are suspended  
   ' and return.  So we need to rewait.  
   Do While Not m_canExecute.WaitOne(0, False)  
              ChangeEvent(m_suspended, True)  
              m_canExecute.WaitOne()  
              ChangeEvent(m_suspended, False)  
   Loop  
  
End Sub  
  
Private Sub CheckAndFireBreakpoint(ByVal events As IDTSComponentEvents, _  
ByVal breakpointID As Integer)  
  
   ' If the breakpoint is enabled, fire it.  
   If m_debugMode <> 0 AndAlso Me.bpm.IsBreakpointTargetEnabled(breakpointID) Then  
              '   Enter a suspend mode before firing the breakpoint.    
              '   Firing the breakpoint will cause the runtime   
              '   to call Suspend on this task.    
              '   Because we are blocked on the breakpoint,   
              '   we are suspended.  
              ChangeEvent(m_suspended, True)  
              events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(breakpointID))  
              ChangeEvent(m_suspended, False)  
   End If  
  
   ' Check for a suspension for two reasons:   
   '   1. If we are at a point where we could fire a breakpoint,   
   '         we are at a valid suspend point.  Even if we didn't hit a  
   '         breakpoint, the runtime may have called suspend,   
   '         so check for it.     
   '   2. Between the return from OnBreakpointHit   
   '         and the reset of the event, it is possible to have  
   '         received a suspend call from which we returned because   
   '         we were already suspended.  We need to be sure it is okay  
   '         to continue executing now.  
   CheckAndSuspend()  
  
End Sub  
  
Shared Sub ChangeEvent(ByVal e As ManualResetEvent, ByVal shouldSet As Boolean)  
  
   Dim succeeded As Boolean  
   If shouldSet Then  
              succeeded = e.Set()  
   Else  
              succeeded = e.Reset()  
   End If  
  
   If (Not succeeded) Then  
              Throw New Exception("Synchronization object failed.")  
   End If  
  
End Sub  
  
Public Property SuspendRequired() As Boolean  
   Get  
               Return m_suspendRequired <> 0  
  End Get  
  Set  
    ' This lock is also taken by Suspend().    
     '   Because it is possible for the package to be  
     '   suspended and resumed in quick succession,   
     '   this property might be set before  
     '   the actual Suspend() call.    
     '   Without the lock, the Suspend() might reset the canExecute  
     '   event after we set it to abort the suspension.  
              SyncLock Me  
                         Interlocked.Exchange(m_suspendRequired,IIf(Value, 1, 0))  
                         If (Not Value) Then  
                                    ResumeExecution()  
                         End If  
              End SyncLock  
   End Set  
End Property  
  
Public Sub ResumeExecution()  
   ChangeEvent(m_canExecute,True)  
End Sub  
  
Public Sub Suspend()  
  
   ' This lock is also taken by the set SuspendRequired method.    
   ' It prevents this call from overriding an   
   ' aborted suspension.  See comments in set SuspendRequired.  
   SyncLock Me  
   ' If a Suspend is required, do it.  
              If m_suspendRequired <> 0 Then  
                         ChangeEvent(m_canExecute, False)  
              End If  
   End SyncLock  
   ' We can't return from Suspend until the task is "suspended".  
   ' This can happen one of two ways:   
   ' the m_suspended event occurs, indicating that the execute thread  
   ' has suspended, or the canExecute flag is set,   
   ' indicating that a suspend is no longer required.  
   Dim suspendOperationComplete As WaitHandle() = {m_suspended, m_canExecute}  
   WaitHandle.WaitAny(suspendOperationComplete)  
  
End Sub  
```  
  
<span data-ttu-id="a7cd4-137">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a7cd4-137">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a7cd4-138">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="a7cd4-138">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a7cd4-139">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="a7cd4-139">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a7cd4-140">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="a7cd4-140">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7cd4-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a7cd4-141">See Also</span></span>  
 [<span data-ttu-id="a7cd4-142">Depurando o fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="a7cd4-142">Debugging Control Flow</span></span>](../../troubleshooting/debugging-control-flow.md)  
  
  
