---
title: Agendando tarefas administrativas automáticas no SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- scheduling administrative tasks [SMO]
- SQL Server Agent [SMO]
- automatic administrative SMO tasks
ms.assetid: 900242ad-d6a2-48e9-8a1b-f0eea4413c16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a7620935a257a4200999cce27ba901588839b16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582387"
---
# <a name="scheduling-automatic-administrative-tasks-in-sql-server-agent"></a><span data-ttu-id="e2502-102">Agendando tarefas administrativas automáticas no SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e2502-102">Scheduling Automatic Administrative Tasks in SQL Server Agent</span></span>
  <span data-ttu-id="e2502-103">No SMO, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent é representado pelos seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="e2502-103">In SMO, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent is represented by the following objects:</span></span>  
  
-   <span data-ttu-id="e2502-104">O objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.JobServer> tem três coleções de trabalhos, alertas e operadores.</span><span class="sxs-lookup"><span data-stu-id="e2502-104">The <xref:Microsoft.SqlServer.Management.Smo.Agent.JobServer> object has three collections of jobs, alerts and operators.</span></span>  
  
-   <span data-ttu-id="e2502-105">O objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.OperatorCollection> representa uma lista de pagers, endereços de email e operadores net send que podem ser notificados sobre eventos automaticamente pelo Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="e2502-105">The <xref:Microsoft.SqlServer.Management.Smo.Agent.OperatorCollection> object represents a list of pager, e-mail addresses and net send operators that can be notified of events automatically by the Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
-   <span data-ttu-id="e2502-106">O objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.AlertCollection> representa uma lista de circunstâncias, tais como eventos do sistema ou condições de desempenho que são monitoradas pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2502-106">The <xref:Microsoft.SqlServer.Management.Smo.Agent.AlertCollection> object represents a list of circumstances such as system events or performance conditions that are monitored by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e2502-107">O objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.JobCollection> é um pouco mais complexo.</span><span class="sxs-lookup"><span data-stu-id="e2502-107">The <xref:Microsoft.SqlServer.Management.Smo.Agent.JobCollection> object is slightly more complex.</span></span> <span data-ttu-id="e2502-108">Ele representa uma lista de tarefas com várias etapas que são executadas em agendas especificadas.</span><span class="sxs-lookup"><span data-stu-id="e2502-108">It represents a list of multi-step tasks that run at specified schedules.</span></span> <span data-ttu-id="e2502-109">As etapas e as informações da agenda são armazenadas nos objetos <xref:Microsoft.SqlServer.Management.Smo.Agent.JobStep> e <xref:Microsoft.SqlServer.Management.Smo.Agent.JobSchedule>.</span><span class="sxs-lookup"><span data-stu-id="e2502-109">The steps and schedule information are stored in the <xref:Microsoft.SqlServer.Management.Smo.Agent.JobStep> and <xref:Microsoft.SqlServer.Management.Smo.Agent.JobSchedule> objects.</span></span>  
  
 <span data-ttu-id="e2502-110">Os objetos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent estão no namespace <xref:Microsoft.SqlServer.Management.Smo.Agent>.</span><span class="sxs-lookup"><span data-stu-id="e2502-110">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent objects are in the <xref:Microsoft.SqlServer.Management.Smo.Agent> namespace.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e2502-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e2502-111">Examples</span></span>  
 <span data-ttu-id="e2502-112">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e2502-112">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="e2502-113">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="e2502-113">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
1.  <span data-ttu-id="e2502-114">Para programas que usam o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent, inclua a instrução `Imports` para qualificar o namespace do Agent.</span><span class="sxs-lookup"><span data-stu-id="e2502-114">For programs that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent, you must include the `Imports` statement to qualify the Agent namespace.</span></span> <span data-ttu-id="e2502-115">Insira a instrução após outras instruções `Imports`, antes de qualquer declaração no aplicativo, como:</span><span class="sxs-lookup"><span data-stu-id="e2502-115">Insert the statement after the other `Imports` statements, before any declarations in the application, such as:</span></span>  
  
 `Imports Microsoft.SqlServer.Management.Smo`  
  
 `Imports Microsoft.SqlServer.Management.Common`  
  
 `Imports Microsoft.SqlServer.Management.Smo.Agent`  
  
## <a name="creating-a-job-with-steps-and-a-schedule-in-visual-basic"></a><span data-ttu-id="e2502-116">Criando um trabalho com etapas e uma agenda no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2502-116">Creating a Job with Steps and a Schedule in Visual Basic</span></span>  
 <span data-ttu-id="e2502-117">Este exemplo de código cria um trabalho com etapas e uma agenda e informa um operador.</span><span class="sxs-lookup"><span data-stu-id="e2502-117">This code example creates a job with steps and a schedule, and then informs an operator.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBAgent1](SMO How to#SMO_VBAgent1)]  -->  
  
## <a name="creating-a-job-with-steps-and-a-schedule-in-visual-c"></a><span data-ttu-id="e2502-118">Criando um trabalho com etapas e uma agenda no Visual C#</span><span class="sxs-lookup"><span data-stu-id="e2502-118">Creating a Job with Steps and a Schedule in Visual C#</span></span>  
 <span data-ttu-id="e2502-119">Este exemplo de código cria um trabalho com etapas e uma agenda e informa um operador.</span><span class="sxs-lookup"><span data-stu-id="e2502-119">This code example creates a job with steps and a schedule, and then informs an operator.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.  
            Server srv = new Server();  
  
            //Define an Operator object variable by supplying the Agent (parent JobServer object) and the name in the constructor.   
            Operator op = new Operator(srv.JobServer, "Test_Operator");  
  
            //Set the Net send address.   
            op.NetSendAddress = "Network1_PC";  
  
            //Create the operator on the instance of SQL Server Agent.   
            op.Create();  
  
            //Define a Job object variable by supplying the Agent and the name arguments in the constructor and setting properties.   
            Job jb = new Job(srv.JobServer, "Test_Job");  
  
            //Specify which operator to inform and the completion action.   
            jb.OperatorToNetSend = "Test_Operator";  
            jb.NetSendLevel = CompletionAction.Always;  
  
            //Create the job on the instance of SQL Server Agent.   
            jb.Create();  
  
            //Define a JobStep object variable by supplying the parent job and name arguments in the constructor.   
            JobStep jbstp = new JobStep(jb, "Test_Job_Step");  
            jbstp.Command = "Test_StoredProc";  
            jbstp.OnSuccessAction = StepCompletionAction.QuitWithSuccess;  
            jbstp.OnFailAction = StepCompletionAction.QuitWithFailure;  
  
            //Create the job step on the instance of SQL Agent.   
            jbstp.Create();  
  
            //Define a JobSchedule object variable by supplying the parent job and name arguments in the constructor.   
  
            JobSchedule jbsch = new JobSchedule(jb, "Test_Job_Schedule");  
  
            //Set properties to define the schedule frequency, and duration.   
            jbsch.FrequencyTypes = FrequencyTypes.Daily;  
            jbsch.FrequencySubDayTypes = FrequencySubDayTypes.Minute;  
            jbsch.FrequencySubDayInterval = 30;  
            TimeSpan ts1 = new TimeSpan(9, 0, 0);  
            jbsch.ActiveStartTimeOfDay = ts1;  
  
            TimeSpan ts2 = new TimeSpan(17, 0, 0);  
            jbsch.ActiveEndTimeOfDay = ts2;  
            jbsch.FrequencyInterval = 1;  
  
            System.DateTime d = new System.DateTime(2003, 1, 1);  
            jbsch.ActiveStartDate = d;  
  
            //Create the job schedule on the instance of SQL Agent.   
            jbsch.Create();  
        }  
```  
  
## <a name="creating-a-job-with-steps-and-a-schedule-in-powershell"></a><span data-ttu-id="e2502-120">Criando um trabalho com etapas e uma agenda no PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2502-120">Creating a Job with Steps and a Schedule in PowerShell</span></span>  
 <span data-ttu-id="e2502-121">Este exemplo de código cria um trabalho com etapas e uma agenda e informa um operador.</span><span class="sxs-lookup"><span data-stu-id="e2502-121">This code example creates a job with steps and a schedule, and then informs an operator.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define an Operator object variable by supplying the Agent (parent JobServer object) and the name in the constructor.  
$op = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.Operator -argumentlist $srv.JobServer, "Test_Operator"  
  
#Set the Net send address.  
$op.NetSendAddress = "Network1_PC"  
  
#Create the operator on the instance of SQL Agent.  
$op.Create()  
  
#Define a Job object variable by supplying the Agent and the name arguments in the constructor and setting properties.   
$jb = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.Job -argumentlist $srv.JobServer, "Test_Job"   
  
#Specify which operator to inform and the completion action.   
$jb.OperatorToNetSend = "Test_Operator";   
$jb.NetSendLevel = [Microsoft.SqlServer.Management.SMO.Agent.CompletionAction]::Always  
  
#Create the job on the instance of SQL Server Agent.   
$jb.Create()  
  
#Define a JobStep object variable by supplying the parent job and name arguments in the constructor.   
$jbstp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.JobStep -argumentlist $jb, "Test_Job_Step"   
$jbstp.Command = "Test_StoredProc";   
$jbstp.OnSuccessAction = [Microsoft.SqlServer.Management.SMO.Agent.StepCompletionAction]::QuitWithSuccess;   
$jbstp.OnFailAction =[Microsoft.SqlServer.Management.SMO.Agent.StepCompletionAction]::QuitWithFailure;   
  
#Create the job step on the instance of SQL Agent.   
$jbstp.Create();   
  
#Define a JobSchedule object variable by supplying the parent job and name arguments in the constructor.   
$jbsch = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.JobSchedule -argumentlist $jb, "Test_Job_Schedule"   
  
#Set properties to define the schedule frequency, and duration.   
$jbsch.FrequencyTypes =  [Microsoft.SqlServer.Management.SMO.Agent.FrequencyTypes]::Daily  
  
$jbsch.FrequencySubDayTypes = [Microsoft.SqlServer.Management.SMO.Agent.FrequencySubDayTypes]::Minute  
$jbsch.FrequencySubDayInterval = 30  
$ts1 =  New-Object -TypeName TimeSpan -argumentlist 9, 0, 0  
$jbsch.ActiveStartTimeOfDay = $ts1  
$ts2 = New-Object -TypeName TimeSpan -argumentlist 17, 0, 0  
$jbsch.ActiveEndTimeOfDay = $ts2  
$jbsch.FrequencyInterval = 1  
$jbsch.ActiveStartDate = "01/01/2003"  
  
#Create the job schedule on the instance of SQL Agent.   
$jbsch.Create();  
```  
  
## <a name="creating-an-alert-in-visual-basic"></a><span data-ttu-id="e2502-122">Criando um alerta no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2502-122">Creating an Alert in Visual Basic</span></span>  
 <span data-ttu-id="e2502-123">Este exemplo de código cria um alerta que é disparado por uma condição de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e2502-123">This code example creates an alert that is triggered by a performance condition.</span></span> <span data-ttu-id="e2502-124">A condição deve ser fornecida em um formato específico:</span><span class="sxs-lookup"><span data-stu-id="e2502-124">The condition must be provided in a specific format:</span></span>  
  
 <span data-ttu-id="e2502-125">**ObjectName | CounterName | Instância | ComparisionOp | Compvalue**</span><span class="sxs-lookup"><span data-stu-id="e2502-125">**ObjectName|CounterName|Instance|ComparisionOp|CompValue**</span></span>  
  
 <span data-ttu-id="e2502-126">É necessário um operador para a notificação de alerta.</span><span class="sxs-lookup"><span data-stu-id="e2502-126">An operator is required for the alert notification.</span></span> <span data-ttu-id="e2502-127">O tipo <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> exige colchetes porque o `operator` é uma palavra-chave do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e2502-127">The <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> type requires square parentheses because `operator` is a Visual Basic keyword.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBAgent3](SMO How to#SMO_VBAgent3)]  -->  
  
## <a name="creating-an-alert-in-visual-c"></a><span data-ttu-id="e2502-128">Criando um alerta no Visual C#</span><span class="sxs-lookup"><span data-stu-id="e2502-128">Creating an Alert in Visual C#</span></span>  
 <span data-ttu-id="e2502-129">Este exemplo de código cria um alerta que é disparado por uma condição de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e2502-129">This code example creates an alert that is triggered by a performance condition.</span></span> <span data-ttu-id="e2502-130">A condição deve ser fornecida em um formato específico:</span><span class="sxs-lookup"><span data-stu-id="e2502-130">The condition must be provided in a specific format:</span></span>  
  
 <span data-ttu-id="e2502-131">**ObjectName | CounterName | Instância | ComparisionOp | Compvalue**</span><span class="sxs-lookup"><span data-stu-id="e2502-131">**ObjectName|CounterName|Instance|ComparisionOp|CompValue**</span></span>  
  
 <span data-ttu-id="e2502-132">É necessário um operador para a notificação de alerta.</span><span class="sxs-lookup"><span data-stu-id="e2502-132">An operator is required for the alert notification.</span></span> <span data-ttu-id="e2502-133">O tipo <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> exige colchetes porque o `operator` é uma palavra-chave do [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2502-133">The <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> type requires square parentheses because `operator` is a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] keyword.</span></span>  
  
```csharp
{  
             //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Define an Alert object variable by supplying the SQL Server Agent and the name arguments in the constructor.   
            Alert al = new Alert(srv.JobServer, "Test_Alert");  
  
            //Specify the performance condition string to define the alert.   
            al.PerformanceCondition = "SQLServer:General Statistics|User Connections||>|3";  
  
            //Create the alert on the SQL Agent.   
            al.Create();  
  
            //Define an Operator object variable by supplying the SQL Server Agent and the name arguments in the constructor.   
  
            Operator op = new Operator(srv.JobServer, "Test_Operator");  
            //Set the net send address.   
            op.NetSendAddress = "NetworkPC";  
            //Create the operator on the SQL Agent.   
            op.Create();  
            //Run the AddNotification method to specify the operator is notified when the alert is raised.   
            al.AddNotification("Test_Operator", NotifyMethods.NetSend);  
        }  
```  
  
## <a name="creating-an-alert-in-powershell"></a><span data-ttu-id="e2502-134">Criando um alerta no PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2502-134">Creating an Alert in PowerShell</span></span>  
 <span data-ttu-id="e2502-135">Este exemplo de código cria um alerta que é disparado por uma condição de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e2502-135">This code example creates an alert that is triggered by a performance condition.</span></span> <span data-ttu-id="e2502-136">A condição deve ser fornecida em um formato específico:</span><span class="sxs-lookup"><span data-stu-id="e2502-136">The condition must be provided in a specific format:</span></span>  
  
 <span data-ttu-id="e2502-137">**ObjectName | CounterName | Instância | ComparisionOp | Compvalue**</span><span class="sxs-lookup"><span data-stu-id="e2502-137">**ObjectName|CounterName|Instance|ComparisionOp|CompValue**</span></span>  
  
 <span data-ttu-id="e2502-138">É necessário um operador para a notificação de alerta.</span><span class="sxs-lookup"><span data-stu-id="e2502-138">An operator is required for the alert notification.</span></span> <span data-ttu-id="e2502-139">O tipo <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> exige colchetes porque o `operator` é uma palavra-chave do [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2502-139">The <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> type requires square parentheses because `operator` is a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] keyword.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define an Alert object variable by supplying the SQL Agent and the name arguments in the constructor.  
$al = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.Alert -argumentlist $srv.JobServer, "Test_Alert"  
  
#Specify the performance condition string to define the alert.  
$al.PerformanceCondition = "SQLServer:General Statistics|User Connections||>|3"  
  
#Create the alert on the SQL Agent.  
$al.Create()  
  
#Define an Operator object variable by supplying the Agent (parent JobServer object) and the name in the constructor.  
$op = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.Operator -argumentlist $srv.JobServer, "Test_Operator"  
  
#Set the Net send address.  
$op.NetSendAddress = "Network1_PC"  
  
#Create the operator on the instance of SQL Agent.  
$op.Create()  
  
#Run the AddNotification method to specify the operator is notified when the alert is raised.  
$ns = [Microsoft.SqlServer.Management.SMO.Agent.NotifyMethods]::NetSend  
$al.AddNotification("Test_Operator", $ns)  
  
#Drop the alert and the operator  
$al.Drop()  
$op.Drop()  
```  
  
## <a name="allowing-user-access-to-subsystem-by-using-a-proxy-account-in-visual-basic"></a><span data-ttu-id="e2502-140">Permitindo o acesso de usuários ao subsistema usando uma conta proxy no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2502-140">Allowing User Access to Subsystem by Using a Proxy Account in Visual Basic</span></span>  
 <span data-ttu-id="e2502-141">Este exemplo de código mostra como permitir o acesso de um usuário a um subsistema especificado usando o método <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount.AddSubSystem%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount>.</span><span class="sxs-lookup"><span data-stu-id="e2502-141">This code example shows how to allow a user access to a specified subsystem by using the <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount.AddSubSystem%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBAgent2](SMO How to#SMO_VBAgent2)]  -->  
  
## <a name="allowing-user-access-to-subsystem-by-using-a-proxy-account-in-visual-c"></a><span data-ttu-id="e2502-142">Permitindo o acesso de usuários ao subsistema usando uma conta proxy no Visual C#</span><span class="sxs-lookup"><span data-stu-id="e2502-142">Allowing User Access to Subsystem by Using a Proxy Account in Visual C#</span></span>  
 <span data-ttu-id="e2502-143">Este exemplo de código mostra como permitir o acesso de um usuário a um subsistema especificado usando o método <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount.AddSubSystem%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount>.</span><span class="sxs-lookup"><span data-stu-id="e2502-143">This code example shows how to allow a user access to a specified subsystem by using the <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount.AddSubSystem%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount> object.</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Declare a JobServer object variable and reference the SQL Server Agent.   
JobServer js = default(JobServer);   
js = srv.JobServer;   
//Define a Credential object variable by supplying the parent server and name arguments in the constructor.   
Credential c = default(Credential);   
c = new Credential(srv, "Proxy_accnt");   
//Set the identity to a valid login represented by the vIdentity string variable.   
//The sub system will run under this login.   
c.Identity = vIdentity;   
//Create the credential on the instance of SQL Server.   
c.Create();   
//Define a ProxyAccount object variable by supplying the SQL Server Agent, the name, the credential, the description arguments in the constructor.   
ProxyAccount pa = default(ProxyAccount);   
pa = new ProxyAccount(js, "Test_proxy", "Proxy_accnt", true, "Proxy account for users to run job steps in command shell.");   
//Create the proxy account on the SQL Agent.   
pa.Create();   
//Add the login, represented by the vLogin string variable, to the proxy account.   
pa.AddLogin(vLogin);   
//Add the CmdExec subsytem to the proxy account.   
pa.AddSubSystem(AgentSubSystem.CmdExec);   
}   
//Now users logged on as vLogin can run CmdExec job steps with the specified credentials.   
```  
  
## <a name="see-also"></a><span data-ttu-id="e2502-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2502-144">See Also</span></span>  
 <span data-ttu-id="e2502-145">[SQL Server Agent](../../../ssms/agent/sql-server-agent.md) </span><span class="sxs-lookup"><span data-stu-id="e2502-145">[SQL Server Agent](../../../ssms/agent/sql-server-agent.md) </span></span>  
 [<span data-ttu-id="e2502-146">Implementar trabalhos</span><span class="sxs-lookup"><span data-stu-id="e2502-146">Implement Jobs</span></span>](../../../ssms/agent/implement-jobs.md)  
