---
title: Usar o provedor do PowerShell para Eventos Estendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], xevent
- extended events [SQL Server], PowerShell
- PowerShell [SQL Server], extended events
ms.assetid: 0b10016f-a479-4444-a484-46cb4677cf64
author: rothja
ms.author: jroth
ms.openlocfilehash: a9efbd389545dcde8285a38b06f41580fb65de6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575124"
---
# <a name="use-the-powershell-provider-for-extended-events"></a><span data-ttu-id="e805a-102">Usar o Provedor do PowerShell para eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="e805a-102">Use the PowerShell Provider for Extended Events</span></span>
  <span data-ttu-id="e805a-103">É possível gerenciar Eventos Estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do uso do provedor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e805a-103">You can manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider.</span></span> <span data-ttu-id="e805a-104">A subpasta XEvent está disponível sob a unidade SQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="e805a-104">The XEvent subfolder is available under the SQLSERVER drive.</span></span> <span data-ttu-id="e805a-105">É possível acessar a pasta por meio do uso de um dos métodos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e805a-105">You can access the folder by using either of the following methods:</span></span>  
  
-   <span data-ttu-id="e805a-106">Em um prompt de comando, digite `sqlps` e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="e805a-106">At a command prompt, type `sqlps`, and then press ENTER.</span></span> <span data-ttu-id="e805a-107">Digite `cd xevent` e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="e805a-107">Type `cd xevent`, and then press ENTER.</span></span> <span data-ttu-id="e805a-108">A partir daí, você pode usar o **CD** e os `dir` comandos (ou o cmdlet **Set-Location** e **Get-ChildItem** ) para navegar até o nome do servidor e o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="e805a-108">From there, you can use the **cd** and `dir` commands (or **Set-Location** and **Get-Childitem** cmdlets) to navigate to the server name and instance name.</span></span>  
  
-   <span data-ttu-id="e805a-109">No Pesquisador de Objetos, expanda o nome de instância, expanda **Gerenciamento**, clique com o botão direito do mouse em **Eventos Estendidos**e clique em **Iniciar PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e805a-109">In Object Explorer, expand the instance name, expand **Management**, right-click **Extended Events**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="e805a-110">Isso inicia o PowerShell no seguinte caminho:</span><span class="sxs-lookup"><span data-stu-id="e805a-110">This starts PowerShell in the following path:</span></span>  
  
     <span data-ttu-id="e805a-111">PS SqlServer: \ XEvent \\ *ServerName* \\ *InstanceName*></span><span class="sxs-lookup"><span data-stu-id="e805a-111">PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*></span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e805a-112">Você pode iniciar o PowerShell em qualquer nó sob **Eventos Estendidos**.</span><span class="sxs-lookup"><span data-stu-id="e805a-112">You can start PowerShell from any node under **Extended Events**.</span></span> <span data-ttu-id="e805a-113">Por exemplo, você pode clicar com o botão direito do mouse em **Sessões**e clicar em **Iniciar PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e805a-113">For example, you can right-click **Sessions**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="e805a-114">Isso inicia o PowerShell um nível mais profundo na pasta de Sessões.</span><span class="sxs-lookup"><span data-stu-id="e805a-114">This starts PowerShell one level deeper, at the Sessions folder.</span></span>  
  
 <span data-ttu-id="e805a-115">Você pode procurar a árvore de pastas XEvent para exibir sessões existentes de Eventos Estendidos e os eventos, destinos e predicados correspondentes associados.</span><span class="sxs-lookup"><span data-stu-id="e805a-115">You can browse the XEvent folder tree to view existing Extended Events sessions and their associated events, targets and predicates.</span></span> <span data-ttu-id="e805a-116">Por exemplo, no caminho PS SqlServer: \ XEvent \\ *ServerName* \\ *InstanceName*>, se você digitar `cd sessions` , pressione Enter, digite `dir` e pressione Enter, você poderá ver a lista de sessões armazenadas nessa instância.</span><span class="sxs-lookup"><span data-stu-id="e805a-116">For example, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*> path, if you type `cd sessions`, press ENTER, type `dir`, and then press ENTER, you can see the list of sessions that are stored on that instance.</span></span> <span data-ttu-id="e805a-117">Você também pode exibir se a sessão está em execução (e nesse caso, há quanto tempo), e se a sessão está configurada para ser iniciada quando a instância for iniciada.</span><span class="sxs-lookup"><span data-stu-id="e805a-117">You can also view whether the session is running (and if this is the case, for how long), and whether the session is configured to start when the instance starts.</span></span>  
  
 <span data-ttu-id="e805a-118">Para exibir os eventos, os predicados e os destinos correspondentes associados a uma sessão, você pode alterar diretórios para o nome da sessão e exibir as pastas de eventos ou de destinos.</span><span class="sxs-lookup"><span data-stu-id="e805a-118">To view the events, their predictates, and the targets that are associated with a session, you can change directories to the session name, and then view either the events or targets folder.</span></span> <span data-ttu-id="e805a-119">Por exemplo, para exibir os eventos e seus predicados associados à sessão de integridade do sistema padrão, do PS SqlServer: \ XEvent \\ *ServerName* \\ *InstanceName*\Sessions> Path, digite `cd system_health\events,` pressione Enter, digite `dir` e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="e805a-119">For example, to view the events and their predicates that are associated with the default system health session, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*\Sessions> path, type `cd system_health\events,` press ENTER, type `dir`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="e805a-120">O provedor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell é uma ferramenta avançada que pode ser usada para criar, alterar e gerenciar sessões de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="e805a-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider is a powerful tool that you can use to create, alter, and manage Extended Events sessions.</span></span> <span data-ttu-id="e805a-121">A seção a seguir fornece alguns exemplos básicos do uso de scripts do PowerShell com Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="e805a-121">The following section provides some basic examples of using PowerShell scripts with Extended Events.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e805a-122">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e805a-122">Examples</span></span>  
 <span data-ttu-id="e805a-123">Nos exemplos a seguir, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e805a-123">In the following examples, note the following:</span></span>  
  
-   <span data-ttu-id="e805a-124">Os scripts devem ser executados no prompt PS SQLSERVER: \\> (disponível digitando `sqlps` em um prompt de comando).</span><span class="sxs-lookup"><span data-stu-id="e805a-124">The scripts must be run from the PS SQLSERVER:\\> prompt (available by typing `sqlps` at a command prompt).</span></span>  
  
-   <span data-ttu-id="e805a-125">Os scripts usam a instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e805a-125">The scripts use the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e805a-126">Os scripts devem ser salvos com uma extensão .ps1.</span><span class="sxs-lookup"><span data-stu-id="e805a-126">The scripts must be saved with a .ps1 extension.</span></span>  
  
-   <span data-ttu-id="e805a-127">A política de execução do PowerShell deve permitir que o script seja executado.</span><span class="sxs-lookup"><span data-stu-id="e805a-127">The PowerShell execution policy must allow the script to run.</span></span> <span data-ttu-id="e805a-128">Para definir a política de execução, use o cmdlet **Set-Executionpolicy** .</span><span class="sxs-lookup"><span data-stu-id="e805a-128">To set the execution policy, use the **Set-Executionpolicy** cmdlet.</span></span> <span data-ttu-id="e805a-129">(Para obter mais informações, digite `get-help set-executionpolicy -detailed` e pressione ENTER.)</span><span class="sxs-lookup"><span data-stu-id="e805a-129">(For more information, type `get-help set-executionpolicy -detailed`, and then press ENTER.)</span></span>  
  
 <span data-ttu-id="e805a-130">O script a seguir cria uma nova sessão denominada 'TestSession.'</span><span class="sxs-lookup"><span data-stu-id="e805a-130">The following script creates a new session that is named 'TestSession'.</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession"  
$event = $session.AddEvent("sqlserver.file_written")  
$event.AddAction("package0.callstack")  
$session.Create()  
```  
  
 <span data-ttu-id="e805a-131">O script a seguir adiciona o destino de buffer de anéis à sessão criada no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e805a-131">The following script adds the ring buffer target to the session that was created in the previous example.</span></span> <span data-ttu-id="e805a-132">(Esse exemplo mostra o uso do método `Alter`.</span><span class="sxs-lookup"><span data-stu-id="e805a-132">(This example shows the use of the `Alter` method.</span></span> <span data-ttu-id="e805a-133">Lembre-se de que você pode adicionar o destino ao criar a sessão pela primeira vez.)</span><span class="sxs-lookup"><span data-stu-id="e805a-133">Be aware that you can add the target when you first create the session.)</span></span>  
  
```powershell
#Script to alter a session.  
cd XEvent  
$h = hostname  
cd $h  
cd DEFAULT\Sessions  
  
#Used to find the specified session.  
$session = dir | where {$_.Name -eq 'TestSession'}  
  
#Add the ring buffer target and call the Alter method.  
$session.AddTarget("package0.ring_buffer")  
$session.Alter()  
```  
  
 <span data-ttu-id="e805a-134">O script a seguir cria uma nova sessão que usa uma expressão de predicado.</span><span class="sxs-lookup"><span data-stu-id="e805a-134">The following script creates a new session that uses a predicate expression.</span></span> <span data-ttu-id="e805a-135">Neste caso, a sessão coleta informações de quando o arquivo c:\temp.log é gravado (por meio do evento sqlserver.file_written).</span><span class="sxs-lookup"><span data-stu-id="e805a-135">In this case, the session collects information for when the c:\temp.log file is written to (through the sqlserver.file_written event).</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession2"  
$event = $session.AddEvent("sqlserver.file_written")  
  
#Construct a predicate "equal_i_unicode_string(path, N'c:\temp.log')".  
$column = $store.SqlServerPackage.EventInfoSet["file_written"].DataEventColumnInfoSet["path"]  
$operand = new-object Microsoft.SqlServer.Management.XEvent.PredOperand -argumentlist $column  
$value = new-object Microsoft.SqlServer.Management.XEvent.PredValue -argumentlist "c:\temp.log"  
$compare = $store.Package0Package.PredCompareInfoSet["equal_i_unicode_string"]  
$predicate = new-object Microsoft.SqlServer.Management.XEvent.PredFunctionExpr -ArgumentList $compare, $operand, $value  
$event.SetPredicate($predicate)  
$session.Create()  
```  
  
## <a name="security"></a><span data-ttu-id="e805a-136">Segurança</span><span class="sxs-lookup"><span data-stu-id="e805a-136">Security</span></span>  
 <span data-ttu-id="e805a-137">Para criar, alterar ou cancelar uma sessão de Eventos Estendidos, você deve ter a permissão ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="e805a-137">To create, alter, or drop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e805a-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e805a-138">See Also</span></span>  
 <span data-ttu-id="e805a-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="e805a-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="e805a-140">[Usar a sessão de system_health](use-the-ssms-xe-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e805a-140">[Use the system_health Session](use-the-ssms-xe-profiler.md) </span></span>  
 [<span data-ttu-id="e805a-141">Ferramentas de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="e805a-141">Extended Events Tools</span></span>](extended-events-tools.md)  
